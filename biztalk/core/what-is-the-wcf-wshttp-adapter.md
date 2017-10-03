---
title: "¿Qué es el adaptador de WCF-WSHttp? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-WSHttp adapters, about WCF-WSHttp adapters
ms.assetid: 183a19e3-10b1-403f-b274-34a441e774d1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5d244dcfe26cf10bc4ae10c63374eef0824444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-wshttp-adapter"></a>¿Qué es el adaptador de WCF-WSHttp?
Puede usar el adaptador de WCF-WSHttp para realizar una comunicación entre equipos con servicios y clientes que puedan comprender los estándares de servicios Web de próxima generación mediante los transportes HTTP o HTTPS con texto o la codificación Message Transmission Optimization Mechanism (MTOM). El adaptador de WCF-WSHtt proporciona acceso completo a características de confiabilidad, seguridad y transacciones de SOAP.  
  
 La siguiente tabla resume las características del adaptador de WCF-WSHttp.  
  
|Description|Característica|  
|-----------------|--------------------|  
|Nivel de interoperabilidad|Perfil de servicios Web WS|  
|Codificación de mensaje|Texto o MTOM|  
|Límite|Entre equipos|  
|Protocolo de transporte|HTTP o HTTPS|  
|Modo de seguridad|Ninguno, Mensaje, Transporte y TransportWithMessageCredential.|  
|Mecanismo de autenticación de cliente|Seguridad de transporte y seguridad de mensaje|  
|Compatibilidad con WS-ReliableMessaging|No|  
|Compatibilidad con WS-AtomicTransaction|Sí|  
|Compatibilidad con mensajería unidireccional|Sí|  
|Compatibilidad con mensajería bidireccional|Sí|  
|Tipo de host para adaptador de recepción|Aislado|  
|Tipo de host para adaptador de envío|En curso|  
  
 El adaptador de WCF-WSHttp se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.  
  
 **Adaptador de recepción de WCF-WSHttp**  
  
 Utilice el adaptador de recepción WCF-WSHttp para recibir solicitudes de Servicio WCF a través del protocolo HTTP o HTTPS. Una ubicación de recepción que usa el adaptador de recepción WCF-WSHttp se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).  
  
 **Adaptador de envío WCF-WSHttp**  
  
 Utilice el adaptador de envío WCF-WSHttp para llamar a un Servicio WCF a través del contrato sin tipo mediante el protocolo HTTP o HTTPS.  
  
 Para obtener más información acerca de WCF de recepción y adaptadores de envío, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de WCF-WSHttp](../core/configuring-the-wcf-wshttp-adapter.md)   
 [Adaptadores de WCF](../core/wcf-adapters.md)