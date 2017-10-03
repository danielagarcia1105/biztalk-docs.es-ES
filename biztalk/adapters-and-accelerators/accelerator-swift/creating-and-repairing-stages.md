---
title: "Creación y reparación de fases | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stages, repair
- stages, create
ms.assetid: 07d7ce7b-ed15-40a7-9c85-280a1d38985b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb87112775b9664badf319796e1a6243cf6eb082
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-repairing-stages"></a>Creación y reparación de fases
La primera etapa en cualquier flujo de trabajo puede ser una fase Create o reparación, es decir, los roles que tienen una capacidad que se define como crean o reparación. El mensaje se origina desde BizTalk MessageBox como un mensaje de error o un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuario crea manualmente un mensaje a través de la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios.  
  
 El creador del mensaje o taller de reparación original es el primer firmante digital del mensaje y agrega su firma digital para el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario después de crear o reparar el mensaje. Esta primera firma no sólo demuestra la identidad del creador del mensaje o taller de reparación, sino que también bloquea el contenido del mensaje en su estado actual. Si se modifica el mensaje después de la primera firma, la pila de firma digital se rompe y advertencias se muestran al usuario que indica que las firmas digitales en el formulario no son válidas.