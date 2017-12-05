---
title: "Quitar la validación de la regla de uso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, deleting rules
- rules
ms.assetid: b2b0dabf-8f99-4b85-95da-6bbf3e79ad41
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 017184e5f530096dc0ca166fdaaa9810a3372cfa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="removing-usage-rule-validation"></a>Quitar la validación de la regla de uso
Reglas de uso se definen en estándares de SWIFT y aplica [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] directivas de negocio específicas para cada tipo de mensaje. Estas reglas de uso son instrucciones que puede usar para proporcionar validación adicional para un campo. A diferencia de las reglas de validación de red, que son obligatorias, puede elegir no exigir reglas de uso para un tipo de mensaje. Si es así, puede realizar una de las siguientes acciones:  
  
-   Puede quitar una regla de negocios específicas que aplica una regla de uso de la directiva de validación de tipo de mensaje.  
  
    > [!IMPORTANT]
    >  Quitar una regla de la directiva lo eliminará permanentemente.  
  
-   Si no desea aplicar ninguna de las reglas de uso, puede anular la implementación de la directiva de validación para un tipo de mensaje.  
  
### <a name="to-remove-a-rule-from-a-policy"></a>Para quitar una regla de una directiva  
  
1.  En un editor de texto, como el Bloc de notas, abra la directiva de validación que se va a cambiar, por ejemplo, MT103_Validation_Policy en  *\<unidad\>*: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category 1\MT103.  
  
2.  Quite el nodo de regla que no desee y, a continuación, guardar la directiva.  
  
3.  Utilice al Asistente para implementación de motor de reglas de negocios para publicar e implementar la directiva.  
  
    > [!NOTE]
    >  También puede quitar una regla de una directiva de validación, cree una copia de la directiva, quitar la regla específica y, a continuación, implementar la Directiva modificada. Anular la implementación de la versión anterior de la directiva.  
  
    > [!NOTE]
    >  En el Compositor de reglas de negocio, no se puede eliminar una regla de una directiva publicada o implementada.  
  
### <a name="to-remove-the-policy-for-a-message-type"></a>Para quitar la directiva para un tipo de mensaje  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Compositor de reglas de negocios**.  
  
2.  En el Explorador de directivas, busque la directiva de validación implementada para el tipo de mensaje, por ejemplo, MT103_Validation_Policy.  
  
3.  Haga clic en la directiva, haga clic en **anular la implementación**, haga clic en **eliminar**y, a continuación, haga clic en **Sí**.