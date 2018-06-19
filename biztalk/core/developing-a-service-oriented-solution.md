---
title: Desarrollar un servicio en la solución orientada a servicios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, developing
- service solution tutorial, background information
- service solution tutorial, developing
- developing, tutorials
- developing, service solution tutorial
ms.assetid: 7979a05c-7fd3-4476-a623-55de8abdc493
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d8e33baa51a551d0f1f851410fda696abc96983
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239332"
---
# <a name="developing-a-service-oriented-solution"></a>Desarrollar un servicio en la solución orientada a servicios
La solución orientada a servicios muestra un sistema de saldo de cuenta de crédito para Woodgrove Bank. Información sobre una cuenta procede de tres sistemas heredados: un sistema SAP que proporciona el límite de crédito, un sistema de transacciones pendientes que se ejecuta en un gran sistema y un sistema de seguimiento de pago con MQSeries. Las solicitudes de comprobación de saldo proceden de un servicio Web o un sistema de respuesta interactiva de voz (IVR). Para obtener más información acerca del escenario, consulte [descripción de la solución orientada a servicios](../core/understanding-the-service-oriented-solution.md).  
  
 Esta Guía del programador presenta un enfoque para la generación de una solución de arquitectura orientada a servicios para el escenario de Woodgrove Bank. La guía comienza teniendo en cuenta una solución posible en cuanto a patrones estándar del sector. La sección “Patrones en la solución orientada a servicios” comienza con la traducción de dicho patrón en los artefactos correspondientes de una aplicación de BizTalk. La siguiente sección, “Componentes de la solución orientada a servicios”, resume las distintas partes de la aplicación y cómo están relacionadas. La sección pone de manifiesto de implementación describen las áreas, como el uso de Enterprise Single Sign-On, que requieren tareas especiales para cumplir los criterios del escenario. La sección “Supervisar la solución orientada a servicios con BAM” describe cómo la solución utiliza la API de BAM para realizar el seguimiento del progreso de las solicitudes y los resultados. Las secciones “Controlar las versiones de la solución orientada a servicios” y “Escalar la solución orientada a servicios” incluyen modos de ampliar o modificar la solución. La sección de referencia muestra los archivos de la solución y suministra una referencia a los mensajes.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Patrones en la solución orientada a servicios](../core/patterns-in-the-service-oriented-solution.md)  
  
-   [Solución orientada a servicios de componentes del servicio](../core/components-of-the-service-oriented-solution.md)  
  
-   [Aspectos destacados de la implementación del servicio en la solución orientada a servicios](../core/implementation-highlights-of-the-service-oriented-solution.md)  
  
-   [El servicio de supervisión orientada a servicios solución con BAM](../core/monitoring-the-service-oriented-solution-with-bam.md)  
  
-   [Solución orientada a servicios de control de versiones del servicio](../core/versioning-the-service-oriented-solution.md)  
  
-   [Escalar la solución orientada a servicios](../core/scaling-the-service-oriented-solution.md)  
  
-   [Referencia de la solución orientada a servicios](../core/service-oriented-solution-reference.md)