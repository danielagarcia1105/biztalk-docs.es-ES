---
title: Cómo configurar la forma construir mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Construct Message shape [Orchestration Designer], configuring
- Construct Message shape [Orchestration Designer]
- configuring [Orchestration Designer], Construct Message shapes
- Construct Message shape [Orchestration Designer], about Construct Message shape
ms.assetid: 8d052b4e-0873-4102-9462-6604423d0524
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07b73e7fe62463767894808d7e95f12cf963e4dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248428"
---
# <a name="how-to-configure-the-construct-message-shape"></a>Cómo configurar la forma Construir mensaje
![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")  
Forma Construir mensaje  
  
 Especifique la variable de mensaje que desee construir y haga nuevas asignaciones al mensaje o sus partes. Todas las asignaciones a un mensaje determinado deben tener lugar dentro de la misma forma Construir mensaje.  
  
 Si desea modificar una propiedad de un mensaje que ya se haya construido, como un mensaje que se haya recibido, debe construir una nueva instancia de mensaje asignando el primero al segundo y modificando la propiedad de la nueva instancia de mensaje. Tanto la construcción como la modificación se realizan dentro de la misma forma Construir mensaje .  
  
### <a name="to-configure-a-construct-message-shape"></a>Para configurar una forma Construir mensaje  
  
1.  En la ventana Propiedades, use el **mensajes construidos** propiedad para especificar qué mensajes de esta forma se construirá.  
  
2.  Agregar y configurar uno o varios **transformar** o **asignación de mensajes** formas dentro de la **forma construir mensaje**.