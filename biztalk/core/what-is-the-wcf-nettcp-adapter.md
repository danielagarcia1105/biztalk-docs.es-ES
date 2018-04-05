---
title: ¿Qué es el adaptador de WCF-NetTcp? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, about WCF-NetTcp adapters
ms.assetid: 94dc24df-19a1-4701-9012-59d05b0c8abd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a741d3a4d7b7bcc80405d0fc25e37a31860523b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-nettcp-adapter"></a>¿Qué es el adaptador de WCF-NetTcp?
El adaptador de WCF-NetTcp proporciona comunicación entre procesos o entre equipos conectados en el mismo equipo en un entorno en el que servicios y clientes se basan en WCF. Proporciona acceso completo a características de confiabilidad, seguridad y transacciones de SOAP. Este adaptador usa el transporte TCP y los mensajes tienen una codificación binaria.  
  
 La siguiente tabla resume las características del adaptador de WCF-NetTcp.  
  
|Description|Característica|  
|-----------------|--------------------|  
|Nivel de interoperabilidad|Perfil de .NET|  
|Codificación de mensaje|Binario|  
|Límite|Entre equipos o entre procesos|  
|Protocolo de transporte|TCP|  
|Modo de seguridad|Ninguno, Mensaje, Transporte y TransportWithMessageCredential.|  
|Mecanismo de autenticación de cliente|Seguridad de transporte y seguridad de mensaje|  
|Compatibilidad con WS-ReliableMessaging|No|  
|Compatibilidad con WS-AtomicTransaction|Sí|  
|Compatibilidad con mensajería unidireccional|Sí|  
|Compatibilidad con mensajería bidireccional|Sí|  
|Tipo de host para adaptador de recepción|En curso|  
|Tipo de host para adaptador de envío|En curso|  
  
 El adaptador de WCF-NetTcp se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.  
  
 **Adaptador de recepción de WCF-NetTcp**  
  
 Utilice el adaptador de recepción WCF-NetTcp para recibir solicitudes de servicio a través del protocolo TCP. Una ubicación de recepción que usa el adaptador de recepción WCF-NetTcp se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).  
  
 **Adaptador de envío WCF-NetTcp**  
  
 Utilice el adaptador de envío WCF-NetTcp para llamar a un Servicio WCF a través del contrato sin tipo mediante el protocolo TCP.  
  
 Para obtener más información acerca de WCF de recepción y adaptadores de envío, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de WCF-NetTcp](../core/configuring-the-wcf-nettcp-adapter.md)   
 [Adaptadores de WCF](../core/wcf-adapters.md)