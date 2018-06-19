---
title: 'Error: referencia raíz de esquema vacía | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.rootRefEmpty
ms.assetid: 172e6ad8-6118-40db-9451-92808a3a2051
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7217f6f9ea328aff4864cfdf3bee9ea71de3741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241924"
---
# <a name="error---schema-root-reference-empty"></a>Error: referencia raíz de esquema vacía
**Código de error**  
  
 BEC2005  
  
 **Explicación**  
  
 El **referencia raíz** propiedad de la **esquema** nodo no está establecido. Cuando el **estándar** propiedad de la **esquema** nodo se establece en un valor distinto de **XML**, debe establecer el **referencia raíz** propiedad indicar qué nodo secundario de la **esquema** nodo está pensado para usarse como la raíz del mensaje definido por este esquema.  
  
 **Acción del usuario**  
  
 Según corresponda para el esquema, establezca el **estándar** propiedad de la **esquema** nodo **XML**, o establecer la **referencia raíz** propiedad de la **esquema** nodo para el nodo secundario correspondiente de la **esquema** nodo. Los siguientes nodos secundarios están disponibles en la **referencia raíz** lista de propiedades de lista desplegable.