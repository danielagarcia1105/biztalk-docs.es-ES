---
title: Cómo exportar una directiva | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], exporting
- policies, exporting
- exporting, policies
ms.assetid: 2e46d96a-7762-479b-be20-bd590b2a4f0a
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 752336e0642c42418f6c68ddefb719d02051d937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254916"
---
# <a name="how-to-export-a-policy"></a>Cómo exportar una directiva
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para exportar una o varias directivas y sus vocabularios asociados.  
  
 Al exportar una directiva, tenga en cuenta los siguientes puntos importantes:  
  
-   Mediante la consola de administración de BizTalk Server, puede exportar directivas desde un grupo de BizTalk o una aplicación de BizTalk, así como los vocabularios que desee. Mediante BTSTask, puede exportar directivas desde una aplicación y también se exportarán todos los vocabularios asociados. En este caso, no existe la posibilidad de seleccionar los vocabularios que va a exportar.  
  
    > [!IMPORTANT]
    >  En el caso de usar la consola de administración, puede seleccionar los vocabularios que quiere exportar. Se recomienda seleccionar todos los vocabularios asociados a una directiva para exportarlos. De esta manera, puede estar seguro de que los vocabularios necesarios se encuentran en el entorno de destino. Aunque los vocabularios necesarios se hayan implementado previamente en el entorno de destino, si su directiva asociada se eliminó, éstos también se habrían eliminado. Esto se debe a que cuando se elimina una directiva, también se eliminan todos sus vocabularios que ninguna otra directiva está usando.  
  
-   Puede, a continuación, importar la directiva o directivas en un grupo de BizTalk diferente o una aplicación en un grupo de BizTalk diferente, como se describe en [cómo importar una directiva](../core/how-to-import-a-policy.md).  
  
-   Para poder exportar una directiva, debe existir en la base de datos del motor de reglas del grupo de BizTalk. Hay varias maneras de importar una directiva en la base de datos de motor de reglas, como se describe en [cómo importar una directiva](../core/how-to-import-a-policy.md).  
  
    > [!NOTE]
    >  Cuando se quita una directiva de la base de datos del motor de reglas mediante el Asistente para implementar el motor de reglas, ésta se seguirá mostrando en la consola de administración aunque no podrá exportarla. Para obtener más información sobre el Asistente para la implementación del motor de reglas, consulte [cómo implementar y anular la implementación de directivas y vocabularios](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).  
  
-   Cuando se usa la consola de administración para la exportación, las directivas y los vocabularios se exportan a un archivo .xml. En cambio, cuando se usa la herramienta de la línea de comandos BTSTask, las directivas y los vocabularios se exportan a un archivo .msi de aplicación.  
  
-   BTSTask no proporciona un comando específico para la exportación de directivas; sin embargo puede usar el comando ExportApp de BTSTask para exportar de forma selectiva únicamente las directivas que desee y no otros artefactos. Esto genera un archivo .msi de aplicación que contiene las directivas. Después, puede usar el comando ImportApp para importar el archivo .msi a un grupo de BizTalk diferente.  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:  
  
-   Es preciso haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
-   El motor de reglas de negocios debe estar instalado. Para obtener más información, consulte [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).  
  
-   La directiva que desee exportar debe existir en la base de datos del motor de reglas del grupo de BizTalk. Si va a exportar la directiva desde una aplicación, ésta también debe haberse agregado a la aplicación.  
  
## <a name="to-export-a-policy"></a>Para exportar una directiva  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server** y expanda el grupo de BizTalk.  
  
3.  Si desea seleccionar las directivas para exportar de todas las directivas en un menú contextual de grupo de BizTalk de la **aplicaciones** carpeta, haga clic en **exportar**y, a continuación, haga clic en **directivas**.  
  
     o  
  
     Si desea exportar las directivas de una aplicación concreta, expanda la carpeta de aplicaciones, haga clic en la aplicación, haga clic en **exportar**y, a continuación, haga clic en **directivas**.  
  
     o  
  
     Si desea exportar sólo una directiva concreta, haga clic en la carpeta de directivas que contiene la directiva, haga clic en la directiva y, a continuación, haga clic en **exportar**.  
  
4.  En la página Exportar directivas, en **directivas para exportar**, seleccione las directivas que se va a exportar.  
  
5.  En **vocabularios que va a exportar**, active las casillas de los vocabularios que va a exportar y desactive las casillas de los vocabularios que no va a exportar. Los vocabularios que esta directiva usa están seleccionados automáticamente.  
  
6.  En **archivo para exportar** , escriba la ruta de acceso del archivo XML que se va a exportar la directiva o directivas y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Use el comando ListApp de BTSTask con la opción /ResourceSpec para generar un archivo XML que enumere los artefactos de la aplicación de BizTalk desde el que desea exportar una directiva, como se describe en [comando ListApp](../core/listapp-command.md).  
  
2.  Edite el archivo XML generado en el paso anterior y elimine todos los artefactos excepto los que correspondan a la directiva o directivas que va a exportar.  
  
3.  Use el comando ExportApp de BTSTask y especifique el archivo XML modificado para el parámetro /ResourceSpec. Para obtener más información, consulte [comando ExportApp](../core/exportapp-command.md).  
  
     BTSTask exporta las directivas especificadas así como todos sus vocabularios asociados a un archivo .msi de aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Exportar aplicaciones de BizTalk, los enlaces y directivas](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [Administración de directivas](../core/managing-policies.md)