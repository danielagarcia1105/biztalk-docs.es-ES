---
title: 'Advertencia: error de coincidencia de tipo de datos de campo | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.fieldDataTypeMismatch
ms.assetid: 0c15d926-1d05-404b-bb16-a5fe8bc3575d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af42f5c921333e34c9ee219020cdb0fba97a7b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288172"
---
# <a name="warning---field-data-type-mismatch"></a>Advertencia: error de coincidencia de tipo de datos de campo
**Código de error**  
  
 BEC1002  
  
 **Explicación**  
  
 El **tipo de datos** se encontró la propiedad del nodo indicado sea diferente de la **tipo de datos** propiedad de la **elemento de campo** nodo al que se está promocionando en el esquema de propiedad correspondiente. El tipo de datos de un nodo en un esquema debe coincidir con el tipo de datos asignado a la **elemento de campo** nodo se utiliza para su promoción de campos de propiedades o, como mínimo, deben asignar los tipos de datos asignado para el mismo tipo de common language runtime (CLR).  
  
 **Acción del usuario**  
  
 Cambiar el **tipo de datos** propiedades del nodo indicado y el **elemento de campo** nodo al que se está promocionando a los mismos datos escribir valor, o al menos para datos de tipo de valores que se asignan al mismo tipo de datos CLR.