---
title: "Configuración de la validación de campos cruzados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f0c6ae8-0b8a-4826-9dfb-bf27e5ff7fa6
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bde88ac82d69cdaa0dec7513e294953b7164b56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-cross-field-validation"></a>Configurar la validación de campos cruzados
Este tema describe cómo habilitar la validación de campos cruzados o segmentos en elementos de datos del conjunto de transacciones en mensajes con codificación EDI Para ello, necesita definir dos valores:  
  
-   Defina la marca de validación de campos cruzados en una anotación del esquema EDI. Para los esquemas HIPAA o X12, se trata de la **X12ConditionDesignator_Check** marca. Para los esquemas EDIFACT, se trata de la **EdifactDependencyRule_Check** marca.  
  
-   Habilite la validación de tipo EDI en las propiedades del acuerdo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="configuring-cross-field-validation"></a>Configurar la validación de campos cruzados  
  
1.  Abra el esquema en el Editor de BizTalk.  
  
2.  En el caso de un X12 o esquema HIPAA, busque el **X12ConditionDesignator_Check** marca una anotación en la sección appinfo del esquema. Establézcalo en **Sí**.  
  
    > [!NOTE]
    >  Si establece la marca X12ConditionDesignator_Check para **Sí** no se puede realizar desde el Editor de esquema de BizTalk. pero puede abrirla en un bloc de notas o en un editor de texto similar, editarla y guardar el archivo de esquema (.xsd).  
  
3.  En el caso de un esquema EDIFACT, busque el **EdifactDependencyRule_Check** marca la anotación en la sección appinfo del esquema. Establézcalo en **Sí**.  
  
4.  Para los segmentos que correspondan del esquema, especifique las condiciones de relación (X12 e HIPAA) o las reglas de dependencia (EDIFACT) que sean de aplicación. Para obtener más información, consulte [validación cruzada de segmentos de campos](../core/cross-field-segment-validation.md).  
  
    > [!NOTE]
    >  Se especifica una regla o condición de validación de campos cruzados para un segmento del esquema EDI. Si especifica una regla de validación de campos cruzados para un elemento de datos en lugar de un segmento, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generará una advertencia cuando se lleve a cabo la validación del esquema.  
  
5.  En el **validación** página (bajo la **configuración del conjunto de transacciones** sección) de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo acuerdo correspondiente, Asegúrese de que el **validación de tipo EDI** propiedad está seleccionada.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de esquemas EDI](../core/developing-edi-schemas.md)