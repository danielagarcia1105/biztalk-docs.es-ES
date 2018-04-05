---
title: ¿Qué es el adaptador de WCF-NetNamedPipe? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, about WCF-NetNamedPipe adapters
ms.assetid: b9f84256-e49d-4ee2-b0fa-d3f692ade1d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c73a670139690c4a27d4784c6ad23225492f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-netnamedpipe-adapter"></a>¿Qué es el adaptador de WCF-NetNamedPipe?
El adaptador de WCF-NetNamedPipe proporciona comunicación entre procesos en el mismo equipo en un entorno en el que servicios y clientes se basan en WCF. Proporciona acceso completo a características de confiabilidad y transacciones de SOAP. El adaptador usa el transporte de canalización mencionado y los mensajes tienen una codificación binaria. Este adaptador no se puede usar en comunicaciones entre equipos.  
  
 La siguiente tabla resume las características del adaptador de WCF-NetNamedPipe.  
  
|Description|Característica|  
|-----------------|--------------------|  
|Nivel de interoperabilidad|Perfil de .NET|  
|Codificación de mensaje|Binario|  
|Límite|Entre procesos|  
|Protocolo de transporte|Canalización con nombre|  
|Modo de seguridad|Ninguno y Transporte|  
|Mecanismo de autenticación de cliente|Seguridad de transporte y seguridad de mensaje|  
|Compatibilidad con WS-ReliableMessaging|No|  
|Compatibilidad con WS-AtomicTransaction|Sí|  
|Compatibilidad con mensajería unidireccional|Sí|  
|Compatibilidad con mensajería bidireccional|Sí|  
|Tipo de host para adaptador de recepción|En curso|  
|Tipo de host para adaptador de envío|En curso|  
  
 El adaptador de WCF-NetNamedPipe se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.  
  
 **Adaptador de recepción de WCF-NetNamedPipe**  
  
 Utilice el adaptador de recepción WCF-NetNamedPipe para recibir solicitudes de Servicio WCF a través del transporte de la canalización con nombre. Una ubicación de recepción que usa el adaptador de recepción WCF-NetNamedPipe se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).  
  
 **Adaptador de envío WCF-NetNamedPipe**  
  
 Utilice el adaptador de envío WCF-NetNamedPipe para llamar a un Servicio WCF mediante el contrato sin tipo a través del transporte de canalización con nombre.  
  
 Para obtener más información acerca de WCF de recepción y adaptadores de envío, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de WCF-NetNamedPipe](../core/configuring-the-wcf-netnamedpipe-adapter.md)   
 [Adaptadores de WCF](../core/wcf-adapters.md)