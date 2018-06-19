---
title: 'Paso 1: Modificar el proyecto de BizTalk vPrev con el adaptador de Siebel | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd95e2-bd51-420f-8156-6f17cc0e91d6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5465a80fd7b75dcbf7ec864b196d2fd5033cb003
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224068"
---
# <a name="step-1-modify-the-vprev-biztalk-project-with-the-siebel-adapter"></a>Paso 1: Modificar el proyecto de BizTalk vPrev con el adaptador de Siebel
![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, realice los siguientes cambios en el proyecto de BizTalk vPrev existente:  
  
-   Generar metadatos para la operación de inserción en el componente de negocio de cuenta mediante basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
-   Asignar el mensaje de solicitud para realizar una operación de inserción con el adaptador de Siebel vPrev a un mensaje de solicitud para realizar una operación de inserción mediante basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
-   Asignar el mensaje de respuesta recibido con basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] al mensaje de respuesta para el adaptador de Siebel vPrev.  
  
## <a name="prerequisite"></a>Requisito previo  
  
-   Debe tener un proyecto de BizTalk vPrev para realizar una operación de inserción en el componente de negocio de la cuenta en el sistema Siebel.  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>Para modificar el proyecto de BizTalk vPrev  
  
1.  Generar metadatos para la operación de inserción en el componente de negocio de cuenta mediante basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Puede usar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar los metadatos.  
  
     Para obtener instrucciones sobre cómo generar los metadatos, consulte [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md). Una vez generado el esquema, un archivo con el nombre similar al *SiebelBindingSchema.xsd* se agrega al proyecto de BizTalk. Este archivo contiene el esquema para enviar un mensaje para realizar la operación de inserción en el componente de negocio de cuenta mediante basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
2.  Generar los metadatos de la operación de inserción, también crea un archivo de enlace de puerto. En el paso siguiente, este archivo de enlace se utilizará para crear un puerto de envío WCF-Custom para enviar mensajes al sistema Siebel. La acción SOAP para la operación también se establece en la operación para el que generar metadatos. Por ejemplo, si genera metadatos para la operación de inserción, el nombre de la operación en la acción de SOAP en el puerto de envío será "Insertar". Sin embargo, la operación de nombre en el puerto de envío lógico que se crea como parte de la orquestación podría ser diferente, por ejemplo, "Operation_1". Como resultado, cuando se envían mensajes al sistema Siebel usando el puerto de envío, recibirá un error. Para evitar esto, asegúrese de que el nombre de la operación en la operación lógica puerto en la orquestación es el mismo que el nombre de la operación para el que generar metadatos de envío.  
  
     Por lo tanto, en el caso de este tutorial, dado que generar metadatos para la operación de inserción, cambiar el nombre de la operación de puerto de envío lógico para "Insertar".  
  
3.  Para el mensaje de solicitud, asignar el esquema generado con el adaptador de Siebel vPrev para el esquema generado mediante basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
    1.  Agregue a un asignador de BizTalk al proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
         En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **RequestMap.btm**. Haga clic en **Agregar**.  
  
    2.  En el panel de esquema de origen, haga clic en **Abrir esquema de origen**.  
  
    3.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema del mensaje de solicitud para el adaptador de Siebel vPrev. Para este tutorial, seleccione *Siebel_BussComp_Migration.AccountService_Account_x5d*. Haga clic en **Aceptar**.  
  
    4.  En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *insertar*y, a continuación, haga clic en **Aceptar**.  
  
    5.  En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.  
  
    6.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema del mensaje de solicitud para basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Para este tutorial, seleccione *Siebel_BussComp_Migration.SiebelDBBindingSchema*y, a continuación, haga clic en **Aceptar**.  
  
    7.  En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *insertar*y, a continuación, haga clic en **Aceptar**.  
  
    8.  Asignar los elementos siguientes en los esquemas de ambos: **Currency_Code**, **Current_Volume**, **Customer_Account_Group**, **ubicación**, **Main_Phone_Number**, **nombre**, **Party_Name**, **Primary_Address_Id**,  
  
    9. Guarde el mapa.  
  
4.  El mensaje de respuesta, asignar el esquema generado con el adaptador de Siebel vPrev el esquema generado mediante basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
    1.  Agregue a un asignador de BizTalk al proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
         En el cuadro de diálogo Agregar nuevo elemento, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como **ResponseMap.btm**. Haga clic en **Agregar**.  
  
    2.  En el panel de esquema de origen, haga clic en **Abrir esquema de origen**.  
  
    3.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de respuesta para basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Para este tutorial, seleccione *Siebel_BussComp_Migration.SiebelDBBindingSchema*. Haga clic en **Aceptar**.  
  
    4.  En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione *InsertResponse* y haga clic en **Aceptar**.  
  
    5.  En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.  
  
    6.  En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de respuesta para el adaptador de Siebel vPrev. Para este tutorial, seleccione *Siebel_BussComp_Migration.AccountService_Account_x5d*. Haga clic en **Aceptar**.  
  
    7.  En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione *InsertResponse* y haga clic en **Aceptar**.  
  
    8.  Mapa de la **matriz: cadena** elemento en el esquema de origen el **expuesto: cadena** elemento en el esquema de destino, como se muestra en la ilustración siguiente.  
  
         ![Asignar los mensajes de respuesta entre versiones de adaptador](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")  
  
    9. Guarde el mapa.  
  
5.  Guarde y compile la solución de BizTalk. Haga clic en la solución y, a continuación, haga clic en **generar solución**.  
  
6.  Implementar la solución. Haga clic en la solución y, a continuación, haga clic en **implementar solución**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear un puerto de envío WCF-custom y configúrelo para utilizar las asignaciones creadas en este paso, como se describe en [paso 2: configurar la orquestación en la consola de administración de BizTalk Server para usar el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 2: Migración de proyectos de BizTalk de Siebel](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)