---
title: Cómo agregar un artefacto de BAM a una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, definition files [BAM]
- BAM, applications
- managing [applications], definition files [BAM]
- definition files [BAM], managing
ms.assetid: 86f19030-e510-4527-ba74-10498c361c00
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44b4a55141b2e5cfbc527dd386c9f1cbdd464dc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247428"
---
# <a name="how-to-add-a-bam-artifact-to-an-application"></a>Cómo agregar un artefacto de BAM a una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para agregar un artefacto de BAM a una aplicación de BizTalk. Al agregar un archivo de definiciones de BAM no se implementa la definición de BAM. La definición de BAM se implementa cuando se importa el archivo .msi de la aplicación.  
  
 Si desea sobrescribir un artefacto de BAM que ya existe en la aplicación, especifique la opción de sobrescritura. La opción de sobrescritura es necesaria sólo cuando el artefacto BAM existente tiene el mismo nombre de archivo que va a agregar. Si no se especifica y artefacto de BAM ya existe en la aplicación con el mismo nombre que el que se agrega, se producirá un error en la operación de agregación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-add-a-bam-artifact-to-an-application"></a>Para agregar un artefacto de BAM a una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **Al Programs**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], el grupo de BizTalk, Aplicaciones y, por último, la aplicación a la que desea agregar un archivo de artefactos de BAM.  
  
3.  Haga clic en el **recursos** carpeta, seleccione **agregar**y, a continuación, haga clic en **recursos**.  
  
4.  Haga clic en **agregar**, seleccione el archivo del artefacto BAM y, a continuación, haga clic en **abiertos**.  
  
5.  En el **tipo de archivo** lista desplegable, seleccione **BizTalk: BAM**.  
  
6.  En **destino**, escriba la ruta de acceso completa de la ubicación donde el archivo de artefacto se copiarán cuando la aplicación se instala desde el archivo .msi, incluido el nombre de archivo. Si no se proporciona esta ruta, el archivo no se copia en el sistema de archivos local durante la instalación; sino que se implementará cuando se importe el archivo .msi de la aplicación.  
  
     Ejemplo: **C:\My Applications\MyBAMfile.xml**  
  
7.  Cuando termine, haga clic en **Aceptar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask AddResource** [**/ApplicationName:***valor*] **/Type:System.BizTalk:Bam** [**/Overwrite**] **/Source:***valor* [**/Destination:***valor*] [**/Server:**  *valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Bam / Overwrite/Source: "C:\Source BAMfiles\MyBAMfile.xml" /Destination:"%BTADInstallDir%\ BAMfiles\MyBAMfile.xml"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega el artefacto de BAM. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/ Tipo**|**BizTalk: BAM** (este valor no distingue entre mayúsculas y minúsculas).|  
    |**/ Sobrescribir**|Opción para sobrescribir un artefacto de BAM existente. Si no se especifica y ya existe un artefacto de BAM en la aplicación que tiene el mismo nombre de archivo que el artefacto de BAM que se agrega, se produce un error en la operación AddResource.|  
    |**Código fuente**|Ruta completa del archivo de artefacto de BAM, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
    |**/ Destino**|Ruta completa de la ubicación en la que se va a copiar el archivo de artefacto de BAM cuando se instale la aplicación desde el archivo .msi. Si no se proporciona, el archivo no se copia al sistema de archivos local durante instalación. Si la ruta incluye espacios, la debe encerrar entre comillas dobles ("). Puede usar la variable de entorno %BTADInstallDir% en la ruta para especificar la carpeta de instalación de la aplicación.|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource (comando): Artefacto de BAM](../core/addresource-command-bam-artifact.md)   
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)   
 [Cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md)