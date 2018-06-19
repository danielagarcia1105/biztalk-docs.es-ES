---
title: Parámetros de ajuste y configuración de adaptador de SOAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], tuning
- SOAP adapters, tuning
ms.assetid: 73c175aa-16b9-4620-b303-9092ae29af21
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be6a71938876ad932a58d369abe40d7c8b073f72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277348"
---
# <a name="soap-adapter-configuration-and-tuning-parameters"></a><span data-ttu-id="e7825-102">Configuración y parámetros de ajuste del adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="e7825-102">SOAP Adapter Configuration and Tuning Parameters</span></span>
<span data-ttu-id="e7825-103">El número de conexiones concurrentes que abre el adaptador de SOAP para un servidor de destino concreto se puede configurar creando una entrada en el archivo BTSNTSvc.exe.config que se encuentra en el directorio raíz de instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e7825-103">You can configure the number of concurrent connections that the SOAP adapter opens for a particular destination server by making an entry in the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7825-104">Esta propiedad se aplicará a los adaptadores de HTTP y de SOAP cuando envíen mensajes al mismo servidor HTTP de destino.</span><span class="sxs-lookup"><span data-stu-id="e7825-104">This property will be applied to both HTTP and SOAP adapters if they send messages to the same destination HTTP server.</span></span> <span data-ttu-id="e7825-105">El valor predeterminado para la propiedad “maxconnnection” es 2, el valor máximo que se puede establecer para la propiedad “maxconnection” para todos los URI es 20.</span><span class="sxs-lookup"><span data-stu-id="e7825-105">The default value for the “maxconnnection” property is 2, the maximum value that can be set for the “maxconnection” property for all URIs is 20.</span></span>  
  
 <span data-ttu-id="e7825-106">El siguiente ejemplo muestra la configuración de la propiedad de número máximo de conexiones:</span><span class="sxs-lookup"><span data-stu-id="e7825-106">The following is an example of the configuration for the maximum connections property:</span></span>  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "20" />  
      <add address = "http://www.northwind.com" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7825-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7825-107">See Also</span></span>  
 <span data-ttu-id="e7825-108">[Configurar el adaptador SOAP](../core/configuring-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e7825-108">[Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="e7825-109">Configuración del adaptador de HTTP y parámetros de ajuste</span><span class="sxs-lookup"><span data-stu-id="e7825-109">HTTP Adapter Configuration and Tuning Parameters</span></span>](../core/http-adapter-configuration-and-tuning-parameters.md)