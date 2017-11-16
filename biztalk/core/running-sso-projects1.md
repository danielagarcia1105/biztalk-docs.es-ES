---
title: Ejecuta SSO Projects1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO projects
- running SSO projects
- samples, SSO projects
ms.assetid: f8da1874-7495-47cd-a3a3-881f722c80a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea316e8f2c78ff718d6821b3f5d063bd86621dd1
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="running-sso-projects"></a><span data-ttu-id="35b0f-102">Ejecución de proyectos SSO</span><span class="sxs-lookup"><span data-stu-id="35b0f-102">Running SSO Projects</span></span>
<span data-ttu-id="35b0f-103">Puede ejecutar el ejemplo desde Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="35b0f-103">You can run the sample  from Internet Explorer.</span></span>  
  
## <a name="running-a-sample-from-internet-explorer"></a><span data-ttu-id="35b0f-104">Ejecución de un ejemplo desde Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="35b0f-104">Running a Sample from Internet Explorer</span></span>  
  
#### <a name="to-run-the-sample-from-the-internet-explorer"></a><span data-ttu-id="35b0f-105">Procedimiento para ejecutar el ejemplo desde Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="35b0f-105">To run the sample from the Internet Explorer</span></span>  
  
1.  <span data-ttu-id="35b0f-106">Abra el explorador.</span><span class="sxs-lookup"><span data-stu-id="35b0f-106">Open your browser.</span></span>  
  
2.  <span data-ttu-id="35b0f-107">Use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="35b0f-107">Use the following syntax:</span></span>  
  
    ```  
    http://localhost/SSODemo/BTSHTTPReceive.dll?[Insert XML Instance body]   
    ```  
  
     <span data-ttu-id="35b0f-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="35b0f-108">For example:</span></span>  
  
     <span data-ttu-id="35b0f-109">http://localhost/SSODemo/BTSHTTPReceive.dll?\<ns0:method_list_method%20xmlns:ns0= "http://microsoft.com/exposed/object/object1">\<ns0:method_list_method>\<ns1:method_list%20xmlns:ns1= "http://microsoft.com/exposed/object">\<ns1:comp_code>\</ns1:comp_code>\<ns1:comp_name>\</ns1:comp_name>\</ns1:object_1>\</ns0:method_list>\</ns0: method_list_method></span><span class="sxs-lookup"><span data-stu-id="35b0f-109">http://localhost/SSODemo/BTSHTTPReceive.dll?\<ns0:method_list_method%20xmlns:ns0="http://microsoft.com/exposed/object/object1">\<ns0:method_list_method>\<ns1:method_list%20xmlns:ns1="http://microsoft.com/exposed/object">\<ns1:comp_code>\</ns1:comp_code>\<ns1:comp_name>\</ns1:comp_name>\< /ns1:object_1>\</ns0:method_list>\</ns0:method_list_method></span></span>  
  
     <span data-ttu-id="35b0f-110">En este caso no es necesario proporcionar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="35b0f-110">In this case you do not have to provide the credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b0f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="35b0f-111">See Also</span></span>  
 [<span data-ttu-id="35b0f-112">Proteger el adaptador</span><span class="sxs-lookup"><span data-stu-id="35b0f-112">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)