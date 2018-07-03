---
title: Implementación de reglas de BRE | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, BRE policies
- BRE policies, deploying
ms.assetid: 3a66aa57-e7f9-400f-963c-eda12fb1e659
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 311a15690dfa63fe18f67ce320310a0ed3339e6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977965"
---
# <a name="deploying-bre-rules"></a>Implementación de reglas de BRE
Debe implementar las reglas BRE utilizadas por [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] orquestaciones para procesar los mensajes de SWIFT.  

 **Resumen**  

 Publicar los vocabularios siguientes:  

- Vocabularios A4SWIFT_CodeLists.XML y A4SWIFT_Functions.xml. Estos se encuentran en  *\<unidad\>*: Acelerador de BizTalk para SWIFT \Program Files\Microsoft \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\< versión\>\Base Policies\Vocabulary. Publicar e implementar estos mediante la utilidad de implementación de BRE.  

  Publicar e implementar las siguientes directivas:  

- Directivas bases SWIFT para el esquema de mensaje, incluidos SWIFT_Reference_Policy.xml SWIFT_PartyIdentifier_Policy.xml y directivas de reglas de red (SWIFT_NetworkRulexxx_Policy.xml) para implementan los esquemas. Estos se encuentran en \<unidad\>: Acelerador de Microsoft BizTalk para SWIFT \Program Files\ \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base directivas. Publicar e implementar estos mediante la utilidad de implementación de BRE.  

- Maestro y validación de directivas asociadas a implementan esquemas de mensaje (MTxxx_Master_Policy.xml y MTxxx_Validation_Policy.xml). Estos se encuentran en \<unidad\>: Acelerador de Microsoft BizTalk para SWIFT \Program Files\ \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category 1\ MTxxx. Publicar e implementar estos mediante la utilidad de implementación de BRE.  

- Maestro y validación de directivas asociadas con la validación de BIC (BIC_Master_Policy.xml y BIC_Validation_Policy.xml), si se requiere validación de BIC. Estos se encuentran en \<unidad\>: Acelerador de Microsoft BizTalk para SWIFT \Program Files\ \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base directivas. Antes de publicar e implementar estas directivas, debe personalizar BIC_Master_Policy.xml con los nombres de SQL Server, el nombre de base de datos BIC e integrado el valor de seguridad. Para obtener más información, consulte [Habilitar validación de códigos de identificación bancarios Forms](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md). Publicar e implementar estos mediante el Asistente para la implementación del motor de reglas.  

### <a name="to-deploy-bre-rules"></a>Para implementar reglas de BRE  

1.  Ejecute la utilidad de implementación de BRE. Para obtener más información, vea "Implementar BRE reglas todas en una vez" a continuación. Esta utilidad publicará e implementará lo siguiente:  

    -   Vocabularios A4SWIFT_CodeLists.XML y A4SWIFT_Functions.xml  

    -   Directivas de bases de SWIFT para el esquema de mensaje, incluidos SWIFT_Reference_Policy.xml SWIFT_PartyIdentifier_Policy.xml y directivas de reglas de red (SWIFT_NetworkRulexxx_Policy.xml)  

    -   Maestro y validación de directivas asociadas a implementan esquemas de mensaje (MTxxx_Master_Policy.xml y MTxxx_Validation_Policy.xml)  

2.  Personalizar BIC_Master_Policy.xml con los nombres de SQL server, el valor de seguridad integrada y nombre de base de datos BIC. Para obtener más información, consulte [Habilitar validación de códigos de identificación bancarios Forms](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).  

3.  Ejecute el Asistente para la implementación de motor de reglas para publicar e implementar BIC_Master_Policy.xml y BIC_Validation_Policy.xml (en \<unidad\>: Acelerador de Microsoft BizTalk para SWIFT \Program Files\ \<versión\> Mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base directivas). Para obtener más información, vea "Implementación de BRE reglas uno at a TIM" a continuación.  

## <a name="tools-for-deploying-the-policies"></a>Herramientas para implementar las directivas  
 Es la manera más fácil de publicar los vocabularios e implementar las directivas mediante la utilidad de implementación del motor de reglas de negocios (BRE) en el Kit de desarrollo de Software (SDK) de A4SWIFT. También puede hacerlo mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] el Asistente para implementar la motor de reglas, que lleva a cabo la directiva o vocabulario de una tarea mismo a la vez.  

> [!NOTE]
>  La utilidad de implementación de BRE no implementa la directiva de maestro de BIC y directiva de validación de BIC. Debe implementar estos con el Asistente para la implementación del motor de reglas.  

### <a name="deploying-bre-rules-all-at-once"></a>Implementar reglas de BRE todos a la vez  
 La utilidad de implementación del motor de reglas de negocios (BRE) realiza una serie de tareas de publicación e implementación en un solo paso. Debe volver a ejecutar la utilidad de implementación cada vez que agregue un esquema al proyecto.  

##### <a name="to-deploy-bre-rules-using-the-bre-deployment-utility"></a>Para implementar reglas BRE mediante la utilidad de implementación de BRE  

1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Acelerador de Microsoft BizTalk para SWIFT**y, a continuación, haga clic en **utilidad de implementación de BRE**.  

2. En el cuadro de diálogo Utilidad de implementación de BRE, haga clic en **examinar**.  

3. En el cuadro de diálogo de la caché Global de ensamblados. NET, seleccione el ensamblado del proyecto que implementó en [implementar esquemas de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)y, a continuación, haga clic en **Aceptar**.  

4. En el cuadro de diálogo Utilidad de implementación de BRE, haga clic en **implementar**.  

   > [!NOTE]
   >  Según los esquemas que se ha implementado con ese ensamblado, la utilidad de implementación identifica las reglas relacionadas y los publica para su uso con el BRE. Cuando haya terminado, la utilidad de implementación de BRE muestra el mensaje siguiente:  

   > [!NOTE]
   >  "La implementación haya finalizado. Ver el archivo de registro o el Compositor de reglas de negocio para obtener más información."  

5. Cierre el cuadro de diálogo Utilidad de implementación de BRE.  

6. Abra [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer. Vaya a \< *unidad*\>: \Documents and Settings\All Users\Application Data y confirme que el archivo de registro BREDeploymentLog.txt aparece en esa unidad.  

7. Reinicie el servicio de actualización de motor de reglas. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, escribiendo **services.msc**y haga clic en **Aceptar**. En el **servicios (Local)** ventana, haga clic en **servicio de actualización de motor de reglas**y, a continuación, haga clic en **reiniciar**.  

### <a name="deploying-bre-rules-one-at-a-time"></a>Implementación de reglas BRE uno a la vez  
 Puede usar al Asistente para la implementación del motor de reglas para publicar vocabularios e implementar directivas de uno a la vez. Para un vocabulario, este proceso implica la importación y publicación del vocabulario a la base de datos desde un archivo en un solo paso. Para una directiva, el proceso implica importar y publicar la directiva en un solo paso y, a continuación, implementarla en otro paso.  

##### <a name="to-deploy-bre-rules-using-the-rules-engine-deployment-wizard"></a>Para implementar reglas BRE mediante el Asistente para la implementación del motor de reglas  

1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Asistente de implementación de motor de Business reglas**.  

2. En la bienvenida a la página del Asistente para la implementación de motor de reglas, haga clic en **siguiente**.  

3. En la página de la tarea de implementación, haga clic en **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, haga clic en **siguiente**.  

4. En la página Directiva Store, en el **lista Nombre de SQL Server**, seleccione el servidor y en el **base de datos de configuración en el servidor seleccionado** lista, seleccione **BizTalkRuleEngineDb**. Haga clic en **Siguiente**.  

5. En la página de archivo del motor de reglas de importación directiva o vocabulario, haga clic en **examinar**.  

6. En la directiva de importación de la página de archivo, en el **buscar en** lista desplegable, desplácese a una de las carpetas siguientes, dependiendo de la directiva o vocabulario:  

   -   \<unidad\>: Acelerador de Microsoft BizTalk para SWIFT \Program Files\ \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base Policies\Vocabulary para A4SWIFT_CodeLists.xml y A4SWIFT_Functions.xml  

   -   \<unidad\>: Acelerador de Microsoft BizTalk para SWIFT \Program Files\ \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base directivas para SWIFT_Reference_Policy.xml, SWIFT_ PartyIdentifier_Policy.xml, directivas de reglas de red, BIC_Master_Policy.xml y BIC_Validation_Policy.xml  

   -   \<unidad\>: Acelerador de Microsoft BizTalk para SWIFT \Program Files\ \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category 1\MTxxx para las directivas de maestro y validación asociados con esquemas de mensaje implementadas  

7. Seleccione la directiva que desea implementar y, a continuación, haga clic en **abierto**.  

8. En la página de archivo del motor de reglas de importación directiva o vocabulario, haga clic en **siguiente**.  

9. En la página Listo, haga clic en **siguiente**.  

10. En la página Importando directiva o vocabulario, compruebe que el comando se realizó correctamente y, a continuación, haga clic en **siguiente**.  

11. Si desea implementar una directiva, en la página Finalización de la página del Asistente para la implementación de motor de reglas, haga clic en **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.  

12. En la bienvenida a la página del Asistente para la implementación de motor de reglas, haga clic en **siguiente**.  

13. En la página de la tarea de implementación, haga clic en **implementar Directiva**y, a continuación, haga clic en **siguiente**.  

14. En la página Directiva Store, en el **lista Nombre de SQL Server**, seleccione el servidor y en el **base de datos de configuración en el servidor seleccionado** lista, seleccione **BizTalkRuleEngineDb**. Haga clic en **Siguiente**.  

15. En la página implementar Directiva, haga clic en la flecha abajo junto a la **directiva del motor de reglas** cuadro de texto, seleccione la directiva que ha publicado y, a continuación, haga clic en **siguiente**.  

16. En la página Listo, haga clic en **siguiente**.  

17. En el **Importando directiva o vocabulario** , comprueba que el comando se realizó correctamente y, a continuación, haga clic en **siguiente**.  

18. Haga clic en **Finalizar**.  

19. Reinicie el **servicio de actualización de motor de reglas**. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, escribiendo **services.msc**y haga clic en **Aceptar**. En el **servicios (Local)** ventana, haga clic en **servicio de actualización de motor de reglas**y, a continuación, haga clic en **reiniciar**.
