##game_server项目异动note
####2016-3-23
> **1、**数据库中Decimal结构导致精度丢失问题。原decimal（10）现decimal(10,2).  
>  fix : 修改表结构  
> reason : 设计表的时候疏漏。
>   
> **2、**code refactor , 代码逻辑修改。  
> before：  
>   
    Boolean ipVerify = mimopayService.ipVerify(ip));
    if (!ipVerify) {
       throw new ErrorException(EnumReturnCode.IP_VERIFY_NOT_PASS);
    }
> ----
    public Boolean ipVerify(String remoteAddr) {
        return callBackIpList.contains(remoteAddr);
    }     
> now：
> 
    mimopayService.ipVerify(request.getHeader(REAL_IP));
>   ----    
    public Boolean ipVerify(String remoteAddr) throws ErrorException {
        if(!callBackIpList.contains(remoteAddr)){
            throw new ErrorException(EnumReturnCode.IP_VERIFY_NOT_PASS);
        }
        return true;
    }
> 修改后感觉逻辑会更改清晰.
 
