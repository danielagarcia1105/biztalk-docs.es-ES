---
title: "Habilita la validación de códigos de identificación del banco | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Bank Identifier Code (BIC), enabling
ms.assetid: d268a892-f304-44cb-b590-28ef359c8d99
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3868906d4f61242b1344a02147e4e71307d67d3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="enabling-validation-of-bank-identifier-codes"></a>Habilita la validación de códigos de identificación del banco
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] esquemas asegurarse de que los códigos de identificación del banco (BICs) especificado en el documento de intercambio SWIFT se ajusta al formato de datos definidos por el SWIFT BIC. A4SWIFT también admite la validación de la BICs con una lista BIC especificado por el cliente en una base de datos.  
  
 Puede realizar esta validación si se ha habilitado la validación de BRE y, a continuación, habilitó la validación de BIC.  
  
 De forma predeterminada, el programa de instalación de A4SWIFT deshabilita la validación de BRE. Para habilitarla, debe establecer el parámetro de configuración de validación de BRE en true para una canalización de recepción que usa el Desensamblador de A4SWIFT. También debe ejecutar la utilidad de implementación del BRE para implementar la directiva principal y la directiva de validación específico en el mensaje que se debe validar (MT*xxx*_Master_policy.xml y MT*xxx*_Validation_Policy.xml). Para obtener más información, consulte [trabajar con las directivas del BRE](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md) y [implementar reglas de BRE](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md).  
  
 Después de haber habilitado la validación del BRE, debe usar publicar e implementar las directivas de validación BIC (BIC_Master_Policy.xml y BIC_Validation_Policy.xml) mediante el Asistente para la implementación del motor de reglas. Antes de hacerlo, debe hacer lo siguiente:  
  
-   Rellenar la base de datos con valores BIC de SWIFT. Puede usar la tabla Bicplus en la base de datos de A4SWIFT, que se instala el programa de instalación de A4SWIFT, o puede usar su propia base de datos personalizada. Para obtener más información, consulte [administración de la tabla Bicplus en la base de datos de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md).  
  
-   Establecer la base de datos BIC y habilitar la validación de BIC personalizando la directiva BIC Master. Vea el siguiente procedimiento.  
  
 Para mejorar el rendimiento, no debería implementar las directivas de validación BIC si no se requiere validación BIC.  
  
> [!NOTE]
>  Puede publicar e implementar la directiva de validación BIC solo si se han publicado los vocabularios A4SWIFT_Codelist y A4SWIFT_Functions. Publicar estos vocabularios mediante la ejecución de la utilidad de implementación del BRE en el ensamblado SWIFTSchemas. Para obtener más información, consulte [lección 1: implementar las reglas de negocios relacionadas](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md).  
  
### <a name="to-customize-the-bic-master-policy"></a>Para personalizar la directiva BIC Master  
  
1.  Abra un editor XML (como el Bloc de notas) y vaya a  **<* unidad*programa de programa\ Microsoft BizTalk Accelerator para SWIFT \<versión\> Pack\SWIFT de mensaje SRG Messages\A4SWIFT\<versión\>\Base directivas **.  
  
2.  Abra **BIC_Master_Policy.xml**. Reemplace las siguientes cadenas existentes con nuevos valores.  
  
    > [!NOTE]
    >  Debe especificar los valores para la tabla de Bicplus en la base de datos de A4SWIFT o su propia base de datos personalizada. La base de datos de A4SWIFT no es el valor predeterminado en BIC_Master_Policy.xml.  
  
    > [!NOTE]
    >  Las siguientes cadenas no deben incluirse entre comillas dobles.  
  
    |Cadena existente|Reemplazar con|  
    |---------------------|------------------|  
    |**ESPECIFIQUE EL NOMBRE DE SQL SERVER**|El nombre de la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] que contiene la base de datos que contiene el código BIC.|  
    |**ESPECIFIQUE EL NOMBRE DE LA BASE DE DATOS DE BIC**|El nombre de la base de datos que contiene la tabla BIC.|  
    |**ESPECIFIQUE EL VALOR DE LA SEGURIDAD INTEGRADA**|**SSPI**|  
  
3.  Guardar la Directiva modificada de Master.  
  
4.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Asistente de implementación de motor de Business reglas**.  
  
5.  En la página de bienvenida, haga clic en **siguiente**.  
  
6.  En la página de la tarea de implementación, haga clic en **importar y publicar la directiva o vocabulario a la base de datos desde un archivo**y, a continuación, haga clic en **siguiente**.  
  
7.  En la página almacén de directivas, en **nombre de SQL Server**, seleccione la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] que contiene las bases de datos de BizTalk. En **base de datos de configuración en el servidor seleccionado**, seleccione **BizTalkRuleEngineDb**y, a continuación, haga clic en **siguiente**.  
  
8.  En la página de archivo de motor de reglas de importación directiva o vocabulario, vaya a  **<* unidad*\Program Files\ Acelerador de Microsoft BizTalk para SWIFT \<versión\> Mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Base directivas **, haga clic en **BIC_Master_Policy.xml**, haga clic en **abiertos**y, a continuación, haga clic en **Siguiente**.  
  
9. En la página Listo, comprobar los datos y, a continuación, haga clic en **siguiente**.  
  
10. En la página Importando directiva o vocabulario, compruebe que el comando se realizó correctamente y, a continuación, haga clic en **siguiente**.  
  
11. En la página Finalización la página Asistente para la implementación de motor de reglas, haga clic en **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.  
  
12. En la página de bienvenida, haga clic en **siguiente**.  
  
13. En la página de la tarea de implementación, haga clic en **implementar Directiva**y, a continuación, haga clic en **siguiente**.  
  
14. En el **almacén de directivas** página **nombre de SQL Server**, seleccione la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] que contiene las bases de datos de BizTalk. En **base de datos de configuración en el servidor seleccionado**, seleccione **BizTalkRuleEngineDb**y, a continuación, haga clic en **siguiente**.  
  
15. En el **implementar Directiva** página, seleccione **BIC_Master_Policy.1.0**y, a continuación, haga clic en **siguiente**.  
  
16. En el **listo** página, haga clic en **siguiente**.  
  
17. En la página implementar la directiva, si la implementación se ha realizado correctamente, haga clic en **siguiente**. Haga clic en **vuelva a ejecutar este asistente**y, a continuación, haga clic en **finalizar**.  
  
18. Repita los pasos 5-17 para **BIC_Validation_Policy.xml**, iniciando **BIC_Validation_Policy** en lugar de **BIC_Master_Policy**.  
  
19. Salir del Asistente para la implementación del motor de reglas.  
  
20. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Compositor de reglas de negocios**. Compruebe que la **directivas** lista incluye **BIC_Master_Policy** y **BIC_Validation_Policy** en **directivas**.  
  
21. Expanda **versión 1.0 - implementada** en **BIC_Master_Policy**y, a continuación, haga clic en **BIC_Master_Rule**.  
  
22. En el panel entonces, compruebe que las propiedades de conexión de SQL que aparecen son correctas.  
  
    > [!NOTE]
    >  A4SWIFT no recoge los cambios realizados en la directiva de validación de BIC principal hasta que se reinicie el servicio de BizTalk que aloja la canalización de recepción que está actualmente configurada para utilizar el Desensamblador SWIFT. A4SWIFT valida todos los documentos que pasan a través de esta canalización para los valores BIC que figuran en la columna BIC especificada en la directiva principal BIC. La cuenta de usuario utilizada para iniciar este servicio de BizTalk (BTSNTSvc.exe) debe tener acceso a la base de datos BIC y la tabla. Para mejorar la seguridad, se recomienda que conceda acceso de solo lectura a la base de datos BIC y la tabla.  
  
    > [!NOTE]
    >  Si se usa reparación de mensajes y nuevo envío, debe reiniciarse el servicio de publicación World Wide Web (mediante la ejecución iisreset.exe) para que la validación de BIC funcionen en InfoPath.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con las directivas del BRE](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)   
 [Administración de la tabla Bicplus en la base de datos de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)