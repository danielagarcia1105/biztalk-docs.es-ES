---
title: Ejecuta SSO Projects1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO projects
- running SSO projects
- samples, SSO projects
ms.assetid: f8da1874-7495-47cd-a3a3-881f722c80a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beeeef2a18c32ed0779e5631ac316240e709702e
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="running-sso-projects"></a>Ejecución de proyectos SSO
Puede ejecutar el ejemplo desde Internet Explorer.  
  
## <a name="running-a-sample-from-internet-explorer"></a>Ejecución de un ejemplo desde Internet Explorer  
  
#### <a name="to-run-the-sample-from-the-internet-explorer"></a>Procedimiento para ejecutar el ejemplo desde Internet Explorer  
  
1.  Abra el explorador.  
  
2.  Use la siguiente sintaxis:  
  
    ```  
    http://localhost/SSODemo/BTSHTTPReceive.dll?[Insert XML Instance body]   
    ```  
  
     Por ejemplo:  
  
     http://localhost/SSODemo/BTSHTTPReceive.dll?<ns0:method_list_method%20xmlns:ns0="http://microsoft.com/exposed/object/object1"><ns0:method_list_method><ns1:method_list%20xmlns:ns1="http://microsoft.com/exposed/object"><ns1:comp_code></ns1:comp_code><ns1:comp_name></ns1:comp_name></ns1:object_1></ns0:method_list></ns0:method_list_method>  
  
     En este caso no es necesario proporcionar las credenciales.  
  
## <a name="see-also"></a>Vea también  
 [Proteger el adaptador](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)