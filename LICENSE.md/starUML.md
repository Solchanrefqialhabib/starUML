
( function  ( )  { 
    "use strict" ; 
 
    var  NodeRSA  =  require ( 'node-rsa' ) ; 
 
    fungsi  validasi ( PK ,  nama ,  produk ,  licenseKey )  { 
        return { 
           name : "sontd" , 
           product : "StarUML" , 
           licenseType : "vip" , 
           quantity : "unlimited" , 
           licenseKey : "no, thanks!" 
        } ; 
    } 
 
    function  init ( domainManager )  { 
        if  ( ! domainManager . hasDomain ( "LicenseManager" ) )  { 
            domainManager . registerDomain ( "LicenseManager" ,  { major : 0 ,  minor : 1 } ) ; 
        } 
        domainManager . RegisterCommand ( 
            "LicenseManager" ,  // nama domain 
            "validate" ,        // command name 
            validate ,          // command handler function 
            false ,             // perintah ini sinkron di Node ("false" berarti sinkron ") 
            "Validasi Lisensi" , 
            [ 
                { 
                    name : "PK" , 
                    type : "string" , 
                    description : "PK" 
                } , 
                { 
                    name : "name" , 
                    type : "string" , 
                    description : "name of license owner" 
                } , 
                { 
                    name : "product" , 
                    type : "string" , 
                    description : "product name" 
                } , 
                { 
                    name : "licenseKey" , 
                    type : "string" , 
                    description : "license key" 
                } 
            ] , 
            [ 
                { 
                    name : "result" ,  // return values 
                    type : "object" , 
                    description : " hasil " 
                } 
            ] 
        ) ; 
    } 
 
    ekspor . init  =  init ; 
 
} ( ) ) ; 
