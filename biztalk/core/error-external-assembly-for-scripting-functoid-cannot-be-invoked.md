---
title: 'Error: ensamblado externo para el Functoid de secuencias de comandos no se puede invocar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.cannotInvokeExternalAssembly
ms.assetid: 30d97b05-2cbf-44a5-b219-3a5ae17fc597
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f6df36a955f2f40da35368fd72fd2d1fcbb7b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240924"
---
# <a name="error---external-assembly-for-scripting-functoid-cannot-be-invoked"></a>No se puede invocar el error: ensamblado externo para el Functoid de secuencias de comandos
**Código de error**  
  
 btm1067  
  
 **Explicación**  
  
 El método de ensamblado externo que está asociado con la correspondiente **secuencias de comandos** no se puede invocar el functoid. Aunque no son necesarios para la compilación de la asignación, la operación Comprobar asignación necesita que dichos ensambladores externos estén presentes en la caché de ensamblados global (GAC). La operación en tiempo de ejecución normal también necesita que estos ensambladores externos estén presentes en la caché de ensamblado global (GAC).  
  
 **Acción del usuario**  
  
 Asegúrese de que el ensamblado externo al que hace referencia la correspondiente **secuencias de comandos** functoid está en la GAC.