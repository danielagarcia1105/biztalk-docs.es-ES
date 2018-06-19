---
title: Invocar reglas de negocios en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], business rules
- business rules, orchestrations
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
- orchestrations, business rules
ms.assetid: ac3a3277-e9ea-4f40-9326-c63076c6b90e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ecbb9738089dfa2d885f9aa45ac12e92ed27aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261828"
---
# <a name="invoking-business-rules-in-orchestrations"></a>Invocar reglas de negocios en orquestaciones
Puede invocar una directiva (o conjunto de reglas) desde una orquestación mediante el uso de la **reglas de llamada** forma. La directiva invoca el motor de reglas, que opera en las reglas de la directiva.  
  
 Además de utilizar reglas de llamada, las reglas de motor puede llamarse mediante programación de la expresión de código, por ejemplo, en un **expresión** o **asignación de mensajes** forma. Para obtener información acerca de la ejecución de directivas mediante programación, vea [cómo ejecutar directivas](../core/how-to-execute-policies.md).  
  
 En esta sección se detalla información de configuración y los procedimientos requeridos para llamar y ejecutar una directiva empresarial desde una orquestación de BizTalk.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información de configuración](../core/configuration-information.md)  
  
-   [Cómo usar la forma reglas de llamada](../core/how-to-use-the-call-rules-shape.md)