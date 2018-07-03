---
title: Habilitar la validación de códigos de identificación bancarios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), enabling
ms.assetid: d268a892-f304-44cb-b590-28ef359c8d99
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fe33576bb23ff40fd80f85281c38a6f5a0ec930
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974173"
---
# <a name="enabling-validation-of-bank-identifier-codes"></a>Habilitar la validación de códigos de identificación bancaria
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] esquemas asegurarse de que los códigos de identificación bancaria (BICs) especificado en el documento de intercambio SWIFT se ajustan al formato de datos definido por el SWIFT BIC. A4SWIFT también admite la validación de la BICs frente a una lista BIC especificado por el cliente en una base de datos.  

 Puede realizar esta validación si se ha habilitado la validación del BRE y, a continuación, habilitó la validación de BIC.  

 De forma predeterminada, el programa de instalación de A4SWIFT deshabilita la validación de BRE. Para habilitarla, debe establecer el parámetro de configuración de validación del BRE en true para una canalización de recepción que usa el Desensamblador de A4SWIFT. También debe ejecutar la utilidad de implementación de BRE para implementar la directiva principal y la directiva de validación específica en el mensaje que se va a validar (MT*xxx*_Master_policy.xml y MT*xxx*_Validation_Policy.xml). Para obtener más información, consulte [trabajar con las directivas del BRE](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md) y [implementar reglas de BRE](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md).  

 Después de haber habilitado la validación del BRE, debe usar publicar e implementar ambas directivas de validación de BIC (BIC_Master_Policy.xml y BIC_Validation_Policy.xml) mediante el Asistente para la implementación del motor de reglas. Antes de hacerlo, debe hacer lo siguiente:  

- Rellenar la base de datos con valores BIC de SWIFT. Puede usar la tabla Bicplus en la base de datos de A4SWIFT, que se instala el programa de instalación de A4SWIFT, o puede usar su propia base de datos personalizada. Para obtener más información, consulte [administración de la tabla Bicplus en la base de datos de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md).  

- Establezca la base de datos BIC y habilitar la validación de BIC mediante la personalización de la directiva de BIC Master. Vea el siguiente procedimiento.  

  Para mejorar el rendimiento, no debería implementar las directivas de validación de BIC si no se requiere validación de BIC.  

> [!NOTE]
>  Puede publicar e implementar la directiva de validación de BIC solo si ha publicado los vocabularios A4SWIFT_Codelist y A4SWIFT_Functions. Publicar estos vocabularios mediante la ejecución de la utilidad de implementación de BRE en el ensamblado SWIFTSchemas. Para obtener más información, consulte [lección 1: implementación de las reglas de negocios relacionados](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md).  

### <a name="to-customize-the-bic-master-policy"></a>Para personalizar la directiva de BIC Master  

1. Abra un editor XML (como el Bloc de notas) y vaya a  **< *unidad*programa de programa\ Microsoft BizTalk Accelerator para SWIFT \<versión\> mensajes de mensaje Pack\SWIFT detención\ A4SWIFT SRG\<versión\>\Base directivas**.  

2. Abra **BIC_Master_Policy.xml**. Reemplace las siguientes cadenas existentes con nuevos valores.  

   > [!NOTE]
   >  Debe especificar valores para la tabla Bicplus en la base de datos de A4SWIFT o su propia base de datos personalizada. La base de datos de A4SWIFT no es el valor predeterminado en BIC_Master_Policy.xml.  

   > [!NOTE]
   >  Las siguientes cadenas no deben incluirse entre comillas dobles.  

   |            Cadena existente            |                                                              Reemplazar con                                                              |
   |---------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
   |      **ESPECIFIQUE EL NOMBRE DE SQL SERVER**      | El nombre de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] que contiene la base de datos que contiene el código BIC. |
   |     **ESPECIFIQUE EL NOMBRE DE LA BASE DE DATOS DE BIC**     |                                         El nombre de la base de datos que contiene la tabla BIC.                                          |
   | **ESPECIFIQUE EL VALOR DE LA SEGURIDAD INTEGRADA** |                                                                **SSPI**                                                                |


3. Guarde la Directiva maestra modificada.  

4. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Asistente de implementación de motor de Business reglas**.  

5. En la página de bienvenida, haga clic en **siguiente**.  

6. En la página de la tarea de implementación, haga clic en **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, haga clic en **siguiente**.  

7. En la página Directiva Store, en **nombre de SQL Server**, seleccione el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] que contiene las bases de datos de BizTalk. En **base de datos de configuración en el servidor seleccionado**, seleccione **BizTalkRuleEngineDb**y, a continuación, haga clic en **siguiente**.  

8. En la página de archivo de directiva o vocabulario del motor de reglas importación, vaya a  **< *unidad*\Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> Pack\SWIFT de mensaje Messages\A4SWIFT SRG\<versión\>\Base directivas**, haga clic en **BIC_Master_Policy.xml**, haga clic en **abierto**y, a continuación, haga clic en **Siguiente**.  

9. En la página Listo, compruebe los datos y, a continuación, haga clic en **siguiente**.  

10. En la página Importando directiva o vocabulario, compruebe que el comando se realizó correctamente y, a continuación, haga clic en **siguiente**.  

11. En la página Finalización la página del Asistente para la implementación de motor de reglas, haga clic en **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.  

12. En la página de bienvenida, haga clic en **siguiente**.  

13. En la página de la tarea de implementación, haga clic en **implementar Directiva**y, a continuación, haga clic en **siguiente**.  

14. En el **directiva Store** página **nombre de SQL Server**, seleccione el [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] que contiene las bases de datos de BizTalk. En **base de datos de configuración en el servidor seleccionado**, seleccione **BizTalkRuleEngineDb**y, a continuación, haga clic en **siguiente**.  

15. En el **implementar Directiva** página, seleccione **BIC_Master_Policy.1.0**y, a continuación, haga clic en **siguiente**.  

16. En el **listo** página, haga clic en **siguiente**.  

17. En la página implementar la directiva, si la implementación se realizó correctamente, haga clic en **siguiente**. Haga clic en **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.  

18. Repita los pasos 5-17 para **BIC_Validation_Policy.xml**, escribiendo **BIC_Validation_Policy** en lugar de **BIC_Master_Policy**.  

19. El Asistente para la implementación del motor de reglas de salida.  

20. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **compositor**. Compruebe que la **directivas** lista incluye **BIC_Master_Policy** y **BIC_Validation_Policy** en **directivas**.  

21. Expanda **versión 1.0 - implementada** en **BIC_Master_Policy**y, a continuación, haga clic en **BIC_Master_Rule**.  

22. En el panel entonces, compruebe que las propiedades de conexión de SQL que aparecen son correctas.  

    > [!NOTE]
    >  A4SWIFT no recoge los cambios realizados en la directiva de validación de BIC principal hasta que reinicie el servicio de BizTalk que aloja la canalización de recepción que actualmente está configurada para usar el Desensamblador de SWIFT. A4SWIFT valida todos los documentos que pasan a través de esta canalización para los valores BIC que figuran en la columna BIC especificada en la directiva principal BIC. La cuenta de usuario utilizada para iniciar este servicio de BizTalk (BTSNTSvc.exe) debe tener acceso a la tabla y la base de datos BIC. Para mayor seguridad, se recomienda que conceda acceso de solo lectura a la tabla y la base de datos BIC.  

    > [!NOTE]
    >  Si usa reparación de mensajes y nuevo envío, debe reiniciarse el servicio de publicación World Wide Web (mediante la ejecución iisreset.exe) para que la validación de BIC funcione desde InfoPath.  

## <a name="see-also"></a>Vea también  
 [Trabajar con las directivas BRE](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)   
 [Administración de la tabla Bicplus en la base de datos de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)