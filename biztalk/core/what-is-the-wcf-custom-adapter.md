---
title: ¿Qué es el adaptador de WCF-Custom? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom adapters, about WCF-Custom adapters
ms.assetid: 7b2178dd-f737-4784-9bcb-e2b3979bfb0d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e090f82bc43d96dc14295af2fac2807cf1fd137
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-custom-adapter"></a>¿Qué es el adaptador de WCF-Custom?
El adaptador de WCF-Custom se utiliza para habilitar el uso de los componentes de extensibilidad de WCF en BizTalk Server. El adaptador habilita una flexibilidad completa del marco de trabajo de WCF. Permite a los usuarios seleccionar y configurar un enlace de WCF para la ubicación de recepción y el puerto de envío. También permite a los usuarios configurar los comportamientos de los extremos y las configuraciones de seguridad.  
  
 El adaptador de WCF-Custom se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío.  
  
 **Adaptador de recepción de WCF-Custom**  
  
 El adaptador de recepción WCF-Custom se usa para recibir solicitudes de servicio de WCF a través de los enlaces, el comportamiento de servicio, el mecanismo de seguridad y el origen del cuerpo del mensaje entrante que seleccionó y configuró en el cuadro de diálogo de las propiedades de transporte de la ubicación de recepción. Una ubicación de recepción que usa el adaptador de recepción WCF-Custom se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).  
  
 **Adaptador de envío WCF-Custom**  
  
 El adaptador de envío de WCF-Custom se usa para llamar a un servicio de WCF a través del contrato sin tipos con los enlaces y el comportamiento de servicio, el mecanismo de seguridad y el origen del cuerpo del mensaje saliente que seleccionó y configuró.  
  
 Para obtener más información acerca de WCF de recepción y adaptadores de envío, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de WCF-Custom](../core/configuring-the-wcf-custom-adapter.md)   
 [Adaptadores de WCF](../core/wcf-adapters.md)