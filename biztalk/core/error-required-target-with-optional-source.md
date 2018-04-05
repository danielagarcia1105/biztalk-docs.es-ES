---
title: 'Error: el destino necesario con origen opcional | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdTargetWithOptionalSource
ms.assetid: 3f342011-4577-4682-8324-8296615d5194
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76dd96f61766a475db6385e306bc64bc36db4fcf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---required-target-with-optional-source"></a>Error: el destino necesario con origen opcional
**Código de error**  
  
 btm1001  
  
 **Explicación**  
  
 Los datos del nodo necesario indicado en el esquema de destino proceden de un nodo opcional del esquema de origen. Por tanto, es probable que haya mensajes de instancia válidos para los que la asignación no se produzca correctamente.  
  
 **Acción del usuario**  
  
 Confirme las características opcionales y necesarias de los nodos especificados de origen y de destino respectivamente, e intente que estas características coincidan.