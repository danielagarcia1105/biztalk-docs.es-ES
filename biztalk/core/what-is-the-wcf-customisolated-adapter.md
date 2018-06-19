---
title: ¿Qué es el adaptador de WCF-CustomIsolated? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-CustomIsolated adapters, about WCF-CustomIsolated adapters
ms.assetid: 872fe97a-8a96-4b2a-8cc1-2db9b315c44f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fdf5a646f586030df6c9492fc6fb2999e49527a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289700"
---
# <a name="what-is-the-wcf-customisolated-adapter"></a>¿Qué es el adaptador de WCF-CustomIsolated?
El adaptador de WCF-CustomIsolated se utiliza para habilitar el uso de los componentes de extensibilidad de WCF en BizTalk Server con un host aislado. El adaptador habilita una flexibilidad completa del marco de trabajo de WCF. Permite a los usuarios seleccionar y configurar un enlace de WCF para la ubicación de recepción y especificar los comportamientos del extremo y la configuración de seguridad. Este adaptador sólo pueden utilizarlo los transportes que estén alojados en Internet Information Server (IIS).  
  
 El adaptador de WCF-CustomIsolated se compone únicamente de un adaptador de recepción. Utilice el adaptador de recepción WCF-CustomIsolated para recibir solicitudes de Servicio WCF a través de enlaces WCF, comportamiento de servicio, comportamiento de extremo, mecanismo de seguridad y el origen del cuerpo del mensaje entrante que haya seleccionado y configurado para la ubicación de recepción que se ejecuta en un host aislado. Una ubicación de recepción que usa el adaptador de recepción WCF-CustomIsolated se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).  
  
 Para obtener más información acerca de WCF adaptadores de recepción, vea [¿cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de WCF-CustomIsolated](../core/configuring-the-wcf-customisolated-adapter.md)   
 [Adaptadores de WCF](../core/wcf-adapters.md)