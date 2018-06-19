---
title: Implementar reglas BRE | Documentos de Microsoft
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
ms.openlocfilehash: 5627731bd84a761ffb62b95646876c768e3298ea
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967899"
---
# <a name="deploying-bre-rules"></a>Implementar reglas BRE
Debe implementar las reglas BRE usadas por [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] orquestaciones para procesar los mensajes de SWIFT.  
  
 **Resumen**  
  
 Publicar los vocabularios siguientes:  
  
-   Vocabularios A4SWIFT_CodeLists.XML y A4SWIFT_Functions.xml. Estos se encuentran en  *\<unidad\>*: \Program Acelerador de BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\< versión\>\Base Policies\Vocabulary. Publique e implemente estas mediante la utilidad de implementación del BRE.  
  
 Publique e implemente las siguientes directivas:  
  
-   Directivas base SWIFT para esquema de mensaje, incluidos SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml y directivas de reglas de red (SWIFT_NetworkRulexxx_Policy.xml) para implementan esquemas. Estos se encuentran en \<unidad\>: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base directivas. Publique e implemente estas mediante la utilidad de implementación del BRE.  
  
-   Maestro y validación de las directivas asociadas a implementan los esquemas de mensaje (MTxxx_Master_Policy.xml y MTxxx_Validation_Policy.xml). Estos se encuentran en \<unidad\>: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category 1\ MTxxx. Publique e implemente estas mediante la utilidad de implementación del BRE.  
  
-   Master y validación las directivas asociadas con la validación de BIC (BIC_Master_Policy.xml y BIC_Validation_Policy.xml), si se requiere validación BIC. Estos se encuentran en \<unidad\>: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base directivas. Antes de publicar e implementar estas directivas, se debe personalizar BIC_Master_Policy.xml con los nombres de SQL Server, el nombre de base de datos BIC y se integra el valor de seguridad. Para obtener más información, consulte [habilitar la validación de Bank identificador códigos](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md). Publique e implemente estos mediante el Asistente para la implementación del motor de reglas.  
  
### <a name="to-deploy-bre-rules"></a>Para implementar reglas BRE  
  
1.  Ejecute la utilidad de implementación de BRE. Para obtener más información, vea "Implementar BRE reglas todas en una vez" a continuación. Esta utilidad se publique e implemente el siguiente:  
  
    -   Vocabularios A4SWIFT_CodeLists.XML y A4SWIFT_Functions.xml  
  
    -   SWIFT directivas base para el esquema de mensaje, incluida la SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml y directivas de reglas de red (SWIFT_NetworkRulexxx_Policy.xml)  
  
    -   Maestro y validación de las directivas asociadas a esquemas de mensaje implementadas (MTxxx_Master_Policy.xml y MTxxx_Validation_Policy.xml)  
  
2.  Personalizar BIC_Master_Policy.xml con los nombres de SQL server, el valor de seguridad integrada y nombre de base de datos BIC. Para obtener más información, consulte [habilitar la validación de Bank identificador códigos](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).  
  
3.  Ejecutar el Asistente para la implementación de motor de reglas para publicar e implementar BIC_Master_Policy.xml y BIC_Validation_Policy.xml (en \<unidad\>: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> Mensaje de Pack\SWIFT Messages\A4SWIFT SRG\<versión\>\Base directivas). Para obtener más información, vea "Implementar BRE reglas de una en una hora" indicada a continuación.  
  
## <a name="tools-for-deploying-the-policies"></a>Herramientas para implementar las directivas  
 Es la manera más fácil de publicar los vocabularios e implementar las directivas mediante la utilidad de implementación del motor de reglas de negocios (BRE) en el Kit de desarrollo de Software (SDK) de A4SWIFT. También puede hacerlo mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] el Asistente para implementar la motor de reglas, que lleva a cabo la directiva o vocabulario de una tarea mismo cada vez.  
  
> [!NOTE]
>  La utilidad de implementación del BRE no implementa la directiva de maestro de BIC y la directiva de validación de BIC. Debe implementarlas mediante el Asistente para implementación de motor de reglas.  
  
### <a name="deploying-bre-rules-all-at-once"></a>Implementar reglas BRE todos a la vez  
 La utilidad de implementación del motor de reglas de negocios (BRE) realiza una serie de tareas de publicación e implementación en un solo paso. Debe volver a ejecutar la utilidad de implementación cada vez que agregue un esquema al proyecto.  
  
##### <a name="to-deploy-bre-rules-using-the-bre-deployment-utility"></a>Para implementar reglas BRE mediante la utilidad de implementación del BRE  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Acelerador de Microsoft BizTalk para SWIFT**y, a continuación, haga clic en **la utilidad de implementación del BRE**.  
  
2.  En el cuadro de diálogo Utilidad de implementación del BRE, haga clic en **examinar**.  
  
3.  En el cuadro de diálogo de la caché Global de ensamblados. NET, seleccione el ensamblado del proyecto que ha implementado en [implementar esquemas de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)y, a continuación, haga clic en **Aceptar**.  
  
4.  En el cuadro de diálogo Utilidad de implementación del BRE, haga clic en **implementar**.  
  
    > [!NOTE]
    >  En función de los esquemas que se ha implementado con ese ensamblado, la utilidad de implementación identifica las reglas relacionadas y los publica para su uso con el BRE. Cuando haya finalizado, la utilidad de implementación del BRE muestra el mensaje siguiente:  
  
    > [!NOTE]
    >  "Implementación se haya completado. Ver el archivo de registro o el Compositor de reglas de negocios para obtener más información".  
  
5.  Cierre el cuadro de diálogo Utilidad de implementación del BRE.  
  
6.  Abra [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] explorador. Vaya a \< *unidad*\>: \Documents and Settings\All Users\Application datos y confirme que el archivo de registro BREDeploymentLog.txt aparece en esa unidad.  
  
7.  Reinicie el servicio de actualización de motor de reglas. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, iniciando **services.msc**y haga clic en **Aceptar**. En el **servicios (Local)** ventana, haga clic en **servicio de actualización de motor de reglas**y, a continuación, haga clic en **reiniciar**.  
  
### <a name="deploying-bre-rules-one-at-a-time"></a>Implementar reglas BRE uno a la vez  
 Puede usar al Asistente para la implementación del motor de reglas para publicar vocabularios e implementar directivas de uno en uno. Para un vocabulario, este proceso implica importar y publicar el vocabulario a la base de datos desde un archivo en un solo paso. Para una directiva, el proceso implica importar y publicar la directiva en un solo paso y, a continuación, implementarlo en otro paso.  
  
##### <a name="to-deploy-bre-rules-using-the-rules-engine-deployment-wizard"></a>Para implementar reglas BRE mediante el Asistente para la implementación del motor de reglas  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Asistente de implementación de motor de Business reglas**.  
  
2.  En la página de bienvenida para el Asistente para la implementación de motor de reglas, haga clic en **siguiente**.  
  
3.  En la página de la tarea de implementación, haga clic en **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, haga clic en **siguiente**.  
  
4.  En la página almacén de directivas, en la **lista de nombre de SQL Server**, seleccione el servidor y en el **base de datos de configuración en el servidor seleccionado** lista, seleccione **BizTalkRuleEngineDb**. Haga clic en **Siguiente**.  
  
5.  En la página de archivo de motor de reglas de importación directiva o vocabulario, haga clic en **examinar**.  
  
6.  En la directiva de importación de la página de archivo, en la **buscar en** lista desplegable, desplácese a una de las carpetas siguientes, dependiendo de la directiva o vocabulario:  
  
    -   \<unidad\>: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base Policies\Vocabulary para A4SWIFT_ CodeLists.xml y A4SWIFT_Functions.xml  
  
    -   \<unidad\>: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base directivas para SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.XML, directivas de reglas de red, BIC_Master_Policy.xml y BIC_Validation_Policy.xml  
  
    -   \<unidad\>: \Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category 1\MTxxx la maestra y validación directivas asociadas a esquemas de mensaje implementadas  
  
7.  Seleccione la directiva que desea implementar y, a continuación, haga clic en **abiertos**.  
  
8.  En la página de archivo de motor de reglas de importación directiva o vocabulario, haga clic en **siguiente**.  
  
9. En la página Listo, haga clic en **siguiente**.  
  
10. En la página Importando directiva o vocabulario, compruebe que el comando se realizó correctamente y, a continuación, haga clic en **siguiente**.  
  
11. Si va a implementar una directiva, en la página Finalización de la página del Asistente de implementación de motor de reglas, haga clic en **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.  
  
12. En la página de bienvenida para el Asistente para la implementación de motor de reglas, haga clic en **siguiente**.  
  
13. En la página de la tarea de implementación, haga clic en **implementar Directiva**y, a continuación, haga clic en **siguiente**.  
  
14. En la página almacén de directivas, en la **lista de nombre de SQL Server**, seleccione el servidor y en el **base de datos de configuración en el servidor seleccionado** lista, seleccione **BizTalkRuleEngineDb**. Haga clic en **Siguiente**.  
  
15. En la página implementar Directiva, haga clic en la flecha abajo junto a la **directiva del motor de reglas** cuadro de texto, seleccione la directiva recién publicado y, a continuación, haga clic en **siguiente**.  
  
16. En la página Listo, haga clic en **siguiente**.  
  
17. En el **Importando directiva o vocabulario** , comprueba que el comando se realizó correctamente y, a continuación, haga clic en **siguiente**.  
  
18. Haga clic en **Finalizar**.  
  
19. Reinicie el **servicio de actualización de motor de reglas**. Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, iniciando **services.msc**y haga clic en **Aceptar**. En el **servicios (Local)** ventana, haga clic en **servicio de actualización de motor de reglas**y, a continuación, haga clic en **reiniciar**.