---
title: Cómo agregar una secuencia de comandos previa y posteriores al procesamiento a una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding scripts
- managing [scripts], applications
- applications, scripts
- managing [scripts], adding
- scripts, adding to applications
- scripts
ms.assetid: 729cb236-b9cf-468a-8b98-a24d86e60d3c
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d0646bc9e896e7b4e4d9264efba7c9bb5f0eb66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248452"
---
# <a name="how-to-add-a-pre--or-post-processing-script-to-an-application"></a>Cómo agregar secuencias de comandos previas y posteriores al procesamiento a una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para agregar una secuencia de comandos previa o posterior al procesamiento a una aplicación. Al agregar una secuencia de comandos a una aplicación, la secuencia de comandos se incluye en el archivo .msi de la aplicación y se ejecuta cuando se importa, se instala o se desinstala la aplicación.  
  
 Al agregar una secuencia de comandos, debe especificar si es una secuencia de comandos previa al procesamiento (que se ejecutará antes de que se importe la aplicación o de que se inicie la instalación) o si se trata de una secuencia de comandos posterior al procesamiento (que se ejecutará después de la importación de la aplicación o cuando finalice la instalación). Secuencias de comandos previas y posteriores al procesamiento se ejecutan también en la desinstalación, en el orden inverso al que se ejecutaron durante la instalación: ejecutan secuencias de comandos previas al procesamiento después de desinstalar y ejecutan scripts posteriores al procesamiento antes de la desinstalación.  
  
 También puede quitar una secuencia de comandos de una aplicación. Para obtener instrucciones, consulte [cómo quitar un previo o procesamiento posterior a la secuencia de comandos de una aplicación](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-add-a-script-to-an-application"></a>Para agregar una secuencia de comandos a una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  Expanda el grupo de BizTalk, expanda Aplicaciones y, a continuación, haga clic con el botón secundario en la carpeta de la aplicación a la que desee agregar una secuencia de comandos.  
  
3.  Seleccione **agregar**, y realice una de las siguientes acciones:  
  
    -   Haga clic en **secuencias de comandos de preprocesamiento** si desea que el script se ejecute antes de importar la aplicación o comienza la instalación o después de la desinstalación.  
  
    -   Haga clic en **secuencias de comandos posteriores al procesamiento** si desea que el script se ejecute después de la instalación o importación de la aplicación, o antes de la desinstalación.  
  
4.  Haga clic en **agregar** y busque el archivo de secuencia de comandos para agregar.  
  
5.  Seleccione el archivo de script y haga clic en **abiertos**.  
  
6.  Si desea sobrescribir un archivo de script que ya existe en la aplicación, seleccione la **sobrescribir todos** casilla de verificación. El archivo de secuencias de comandos debe tener el mismo nombre de archivo que el que se va agregar para sobrescribirse. De no ser así, se agregará la secuencia de comandos nueva, y la existente permanecerá en la aplicación sin cambios.  
  
7.  Haga clic en el **tipo de archivo** lista desplegable y haga clic en el tipo de archivo: **System.BizTalk:PreprocessingScript** o **System.BizTalk:PostprocessingScript**.  
  
8.  Si es necesario, en **ubicación de destino** tipo de archivo que se para pueden copiar cuando la aplicación está instalada la ruta de acceso donde desea que el script y, a continuación, haga clic en **Aceptar**. La ruta predeterminada instalará la secuencia de comandos en la carpeta de instalación de la aplicación (%BTAD_InstallDir%).  
  
> [!NOTE]
>  Si no proporciona la ruta, la secuencia de comandos no se copiará en el sistema de archivos local durante la instalación. Si la secuencia de comandos se debe ejecutar cuando la aplicación esté desinstalada, asegúrese de proporcionar esta ruta; de lo contrario, la secuencia de comandos no estará presente en el sistema de archivos local y no se ejecutará durante la desinstalación.  
  
 La secuencia de comandos se agrega a la aplicación y se muestra en la carpeta Recursos de la aplicación.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask AddResource** [**/ApplicationName:***valor*] **/Type:System.BizTalk:PreProcessingScript**&#124; **System.BizTalk:PostProcessingScript** [**/Overwrite**] **/Source:***valor* [**/Destination:**  *valor*] [**/Server:***valor*] [**/Database:***valor*] [  **/Property: args = "**  *lista de argumentos***"**]  
  
     Ejemplo:  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:PreProcessingScript / Overwrite/Source: "C:\Source Scripts\MyScript.vbs" /Destination: "C:\New Scripts\MyScript.vbs" /Server:MyDatabaseServer /Database:BizTalkMgmtDb / Property: args = "argumento1 argumento2"**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega la secuencia de comandos. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/ Tipo**|**System.BizTalk:PreProcessingScript** o **System.BizTalk:PostProcessingScript**, según el tipo de script que se va a agregar. Use **System.BizTalk:PreProcessingScript** si desea que el script se ejecute antes de importar la aplicación o la instalación o después de la desinstalación. Use **System.BizTalk:PostProcessingScript** si desea que el script se ejecute después de la instalación o importación de la aplicación, o antes de la desinstalación.|  
    |**/ Sobrescribir**|Actualice una secuencia de comandos existente. Si no se especifica y ya existe un archivo de secuencias de comandos en la aplicación que tiene el mismo nombre que el archivo de secuencia de comandos que se agrega, se producirá un error en la operación de agregación.|  
    |**Código fuente**|Ruta completa del archivo de secuencia de comandos, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
    |**/ Destino**|Ruta completa de la ubicación en la que se va a copiar el archivo de secuencias de comandos cuando se instale la aplicación desde el archivo MSI. Si no se proporciona, el archivo no se copia al sistema de archivos local durante instalación. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
    |**/ Property: args =**|Cero o más argumentos. Los argumentos que se proporcionen aquí pasarán a la secuencia de comandos cuando ésta se invoque.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar secuencias de comandos previas y posteriores al procesamiento](../core/managing-pre-and-post-processing-scripts.md)   
 [AddResource (comando): Secuencia de comandos de preprocesamiento](../core/addresource-command-preprocessing-script.md)   
 [El comando AddResource: Secuencias de comandos](../core/addresource-command-postprocessing-script.md)