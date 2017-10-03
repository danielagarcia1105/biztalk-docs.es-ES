---
title: "Parámetros de ajuste y configuración de adaptador de SOAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], tuning
- SOAP adapters, tuning
ms.assetid: 73c175aa-16b9-4620-b303-9092ae29af21
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be6a71938876ad932a58d369abe40d7c8b073f72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="soap-adapter-configuration-and-tuning-parameters"></a>Configuración y parámetros de ajuste del adaptador de SOAP
El número de conexiones concurrentes que abre el adaptador de SOAP para un servidor de destino concreto se puede configurar creando una entrada en el archivo BTSNTSvc.exe.config que se encuentra en el directorio raíz de instalación de BizTalk Server.  
  
> [!NOTE]
>  Esta propiedad se aplicará a los adaptadores de HTTP y de SOAP cuando envíen mensajes al mismo servidor HTTP de destino. El valor predeterminado para la propiedad “maxconnnection” es 2, el valor máximo que se puede establecer para la propiedad “maxconnection” para todos los URI es 20.  
  
 El siguiente ejemplo muestra la configuración de la propiedad de número máximo de conexiones:  
  
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
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador SOAP](../core/configuring-the-soap-adapter.md)   
 [Configuración del adaptador de HTTP y parámetros de ajuste](../core/http-adapter-configuration-and-tuning-parameters.md)