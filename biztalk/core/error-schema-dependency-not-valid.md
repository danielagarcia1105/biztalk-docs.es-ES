---
title: Error - dependencia de esquemas no válida | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.schemaDependencyNotValid
ms.assetid: 431278f0-6cd1-4b3f-8d87-16af4991d354
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36326608f191b520c41cb42890aec029c432fd30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-dependency-not-valid"></a>Error - dependencia de esquemas no válida
**Código de error**  
  
 BEC2009  
  
 **Explicación**  
  
 Todos los esquemas dependientes, como aquellos que se importan, incluyen o redefinen en el esquema en uso, deben agregarse al proyecto de BizTalk o existir en un ensamblado al que haga referencia este proyecto. Esquema incluso **importar**, **incluyen**, y **redefinir** directivas que especifican esquemas en un sitio Web remoto deben agregarse a este proyecto de BizTalk.  
  
 **Acción del usuario**  
  
 Use la **Agregar elemento existente** comando el **archivo** menú y el menú contextual para el proyecto de Microsoft® BizTalk® Server para agregar todos los esquemas que depende este esquema al proyecto de BizTalk. Es probable que necesite descargar estos esquemas de un sitio Web en el disco duro local antes de agregarlos al proyecto de BizTalk.