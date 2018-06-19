---
title: Solución orientada a servicios de control de versiones del servicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, service solutions
- service solution tutorial, versioning
ms.assetid: 0e09720f-53f2-4b38-aae3-a79ddfd35be5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af1c5d1475fc37322be9a8483963bbfd1432fbb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287644"
---
# <a name="versioning-the-service-oriented-solution"></a>Solución orientada a servicios de control de versiones del servicio
Las dos orquestaciones que actúan como servidores front-end a la solución, **CustomerServiceReceiveSend** y **CustomerServiceNativeRequestResponse**, llame a la central, la orquestación de trabajo,  **CustomerService**. Las llamadas a la orquestación dependen del número de versión del ensamblado que contiene la orquestación. Dado que las tres orquestaciones están en el mismo ensamblado, no hay ningún problema de control de versiones.  
  
 Además, el proceso empresarial que implementan las orquestaciones es un proceso de solicitud-respuesta muy efímero que se ejecuta rápidamente. Por lo tanto, la pregunta de versiones del proceso empresarial no se da en esta solución, no hay ninguna orquestación diferente en distintos ensamblados con distintas versiones.  
  
 Sin embargo, las orquestaciones utilizan los esquemas del ensamblado de esquema. Si los esquemas se revisan y compilan en una versión diferente, debe volver a compilar las orquestaciones con la versión más nueva del ensamblado de esquema.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar un servicio en la solución orientada a servicios](../core/developing-a-service-oriented-solution.md)