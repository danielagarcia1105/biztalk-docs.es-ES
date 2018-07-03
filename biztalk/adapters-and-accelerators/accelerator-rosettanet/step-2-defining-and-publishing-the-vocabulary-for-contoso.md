---
title: 'Paso 2: Definición y publicación del vocabulario de Contoso | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- vocabularies, creating
- vocabularies, publishing
- private process tutorial, creating vocabularies
ms.assetid: e23880c0-772c-48c6-a6b5-32eb951527c8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56dc5a4c65dcf198308e382b82d9b167c5d4ca8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007109"
---
# <a name="step-2-defining-and-publishing-the-vocabulary-for-contoso"></a>Paso 2: Definición y publicación del vocabulario de Contoso
En este escenario, Contoso implementa una directiva empresarial que se asegura de que el inventario está siempre disponible si se produce una emergencia. Crear directivas de negocio mediante el Compositor de reglas de negocios en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. En este paso, creará el vocabulario que se va a usar al definir la directiva empresarial.  
  
### <a name="to-add-a-new-vocabulary"></a>Para agregar un vocabulario nuevo  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **compositor**.  
  
2. En el cuadro de diálogo Abrir almacén de reglas, haga clic en **Aceptar**.  
  
3. En el panel Explorador de hechos, en la ficha **Vocabularios** , haga clic con el botón derecho en **Vocabularios**y, a continuación, haga clic en **Agregar nuevo vocabulario**.  
  
4. Asigne al vocabulario el nombre **3A2PriceAvailabilityVocabulary**y, a continuación, presione **Entrar**.  
  
### <a name="to-define-a-constant-vocabulary-value"></a>Para definir un valor constante de vocabulario  
  
1.  En el Compositor de reglas de negocio, haga clic en **3A2PriceAvailabilityVocabulary**, haga clic con el botón derecho en **Versión 1.0 (sin guardar)** y, a continuación, haga clic en **Agregar nueva definición**.  
  
2.  En la página **Asistente para definición de vocabulario** , seleccione **Valor, rango de valores o conjunto de valores constantes**y, a continuación, haga clic en **Siguiente**.  
  
3.  En la página **Valor, rango de valores o conjunto de valores constantes** , en el cuadro **Nombre de definición** , escriba **Cantidad de emergencia necesaria**y, a continuación, haga clic en **Siguiente**.  
  
4.  En la página **Definir un valor constante** , en el cuadro **Valor** , escriba **800**y, a continuación, haga clic en **Finalizar**.  
  
### <a name="to-define-an-xml-document-get-element"></a>Para definir un elemento "Get" de documento XML  
  
1.  En el Compositor de reglas de negocio, en el Explorador de hechos, haga clic con el botón derecho en **Versión 1.0 (sin guardar)** en **3A2PriceAvailabilityVocabulary**y, a continuación, haga clic en **Agregar nueva definición**.  
  
2.  En el **VocabularyDefinition asistente** página, seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.  
  
3.  En la página **Atributo o elemento de documento XML** , en el cuadro **Nombre de definición** , escriba **Cantidad disponible**.  
  
4.  Haga clic en **Examinar** (junto al campo **Esquema** ), vaya al proyecto **ContosoPriceAndAvailability** en la carpeta de la solución, seleccione el esquema **ContosoPriceAndAvailability.xsd** y, a continuación, haga clic en **Abrir**.  
  
5.  En el cuadro de diálogo Seleccionar enlace, expanda **rootPriceResponse**y después **Productos**, seleccione el elemento **NumberAvailable** y, a continuación, haga clic en **Aceptar**.  
  
6.  En la página **Atributo o elemento de documento XML** , en el cuadro **Tipo de documento** , asegúrese de que el valor es **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.  
  
7.  En la sección **Seleccionar operación** , seleccione **Realizar operación "Get"** y, a continuación, haga clic en **Finalizar**.  
  
### <a name="to-define-an-xml-document-set-element"></a>Para definir un elemento "Set" de documento XML  
  
1.  En el Compositor de reglas de negocio, en el Explorador de hechos, haga clic con el botón derecho en **Versión 1.0 (sin guardar)** en **3A2PriceAvailabilityVocabulary**y, a continuación, haga clic en **Agregar nueva definición**.  
  
2.  En el **VocabularyDefinition asistente** página, seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.  
  
3.  En la página **Atributo o elemento de documento XML** , en el cuadro **Nombre de definición** , escriba **Cantidad final disponible**.  
  
4.  Haga clic en **Examinar** (junto al campo **Esquema** ), vaya al proyecto **ContosoPriceAndAvailability** en la carpeta de la solución, seleccione el esquema **ContosoPriceAndAvailability.xsd** y, a continuación, haga clic en **Abrir**.  
  
5.  En el **Seleccionar enlace** cuadro de diálogo, expanda **rootPriceResponse**, expanda **productos**y, a continuación, seleccione el **NumberAvailable** elemento. Haga clic en **Aceptar**.  
  
6.  En la página **Atributo o elemento de documento XML** , en el cuadro **Tipo de documento** , asegúrese de que el valor es **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.  
  
7.  En la sección **Seleccionar operación** , seleccione **Realizar operación "Set"** y, a continuación, haga clic en **Siguiente**.  
  
8.  En la página **Especificar el nombre para mostrar** , haga clic en **Finalizar**.  
  
### <a name="to-save-and-publish-the-vocabulary"></a>Para guardar y publicar el vocabulario  
  
1.  En el Compositor de reglas de negocio, en el Explorador de hechos, haga clic con el botón derecho en **Versión 1.0 (sin guardar)** en **3A2PriceAvailabilityVocabulary**y, a continuación, haga clic en **Guardar**.  
  
2.  Haga clic con el botón derecho en el mismo nodo de **Versión 1.0** y, a continuación, haga clic en **Publicar**.  
  
    > [!NOTE]
    >  Deje el Compositor de reglas de negocio abierto para el siguiente paso del tutorial.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Definición, publicación e implementación de la directiva empresarial de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)