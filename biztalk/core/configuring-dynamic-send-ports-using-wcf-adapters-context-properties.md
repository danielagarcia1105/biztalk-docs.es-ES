---
title: Configuración de puertos de envío dinámicos mediante las propiedades de contexto de adaptadores de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, send ports
- send ports, WCF services
- dynamic send ports, WCF services
- send ports, dynamic
ms.assetid: 2a7e2cd2-fa2d-45da-bb8e-eb8bab21bfa3
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca781dc1d101e3eef0976229b3d1b986c2f4498d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995277"
---
# <a name="configuring-dynamic-send-ports-using-wcf-adapters-context-properties"></a>Configurar puertos de envío dinámico mediante el uso de propiedades de contexto de adaptadores de WCF
Puede configurar puertos de envío dinámico para adaptadores de WCF. El URI, acción y el enlace es posible que se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** dar forma, como se muestra en el siguiente adaptador de WCF-NetTcp:  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.SecurityMode)="Transport";  
MessageOut(WCF.TransportClientCredentialType)="Windows";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/netTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-NetTcp";  
```  
  
 El código siguiente muestra un ejemplo de cómo especificar las propiedades de contexto WCF en el **expresión** forma para un adaptador de WCF-Custom:  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.BindingType)="customBinding";  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.BindingConfiguration)=@"<binding name=""customBinding""><binaryMessageEncoding /><tcpTransport /></binding>";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/customNetTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
 Al especificar propiedades de contexto de WCF, debe tenerse en cuenta lo siguiente:  
  
- Hay direcciones que pueden asignarse a diversos adaptadores. Por ejemplo, una dirección que empieza por http:// o https:// puede controlarla el adaptador de HTTP, así como los adaptadores WCF-BasicHttp, WCF-WsHttp o WCF-Custom. Para ver otro ejemplo, en el código de ejemplo expuesto anteriormente, ambos usan la dirección que empieza por net.tcp://, y dado que el segundo código de ejemplo usa el enlace personalizado, el adaptador de WCF-Custom debe usarse para controlar la dirección. Por lo tanto, para identificar el adaptador correcto, debe configurar el elemento opcional **Microsoft.XLANGs.BaseTypes.TransportType** campo un **expresión** con el adaptador que desea usar.  
  
  > [!NOTE]
  >  Si la dirección empieza por http:// o https:// y no se especifica la **Microsoft.XLANGs.BaseTypes.TransportType** campo, de forma predeterminada, el motor de BizTalk usará el adaptador de HTTP.  
  
- El **WCF. BindingType** identifica el enlace por nombre. Puede tener uno de los valores siguientes:  
  
  - basicHttpBinding  
  
  - customBinding  
  
  - netMsmqBinding  
  
  - netNamedPipeBinding  
  
  - netTcpBinding  
  
  - wsFederationHttpBinding  
  
  - wsHttpBinding  
  
    La lista anterior puede ampliarse. Por ejemplo, puede agregar su propio enlace, como FtpBinding.  
  
- El **WCF. BindingConfiguration** especifica la configuración de enlace para el tipo de enlace. Toma cualquier enlace registrado en el archivo de configuración del equipo. También toma la configuración XML en el mismo formato usado en la configuración del enlace del archivo de configuración WCF.  
  
- Puede que tenga que especificar propiedades de WCF adicionales. Puede escribir **WCF** en el Editor de expresiones y IntelliSense característica debe enumerar todas las propiedades de contexto disponibles. Para obtener más información acerca de las propiedades de contexto WCF, vea [propiedades y esquema de propiedades de adaptadores de WCF](../core/wcf-adapters-property-schema-and-properties.md).  
  
  Los ejemplos anteriores muestran cómo configurar **WCF. Acción** con una sola acción. Para varios escenarios de asignación de acciones, el adaptador de WCF no es compatible con el uso de varias asignaciones de acciones con puertos de envío dinámicos. Solo puede establecer la acción real el **WCF. Acción** propiedad de contexto como se muestra anteriormente.  
  
## <a name="see-also"></a>Vea también  
 [Adaptadores de envío de la especificación de acciones SOAP de WCF](../core/specifying-soap-actions-for-wcf-send-adapters.md)   
 [Cómo usar expresiones para asignar valores a puertos dinámicos](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)   
 [Enlaces de puertos](../core/port-bindings.md)