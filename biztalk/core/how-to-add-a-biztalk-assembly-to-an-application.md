---
title: Cómo agregar un ensamblado de BizTalk a una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding assemblies
- assemblies, applications
- managing [assemblies], adding to applications
- applications, assemblies
- managing [assemblies], applications
ms.assetid: 1525a0f6-cb0f-43bf-a851-40c06ab2135e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9165415ec736c7cf9f4716e8fb183395602a687d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009349"
---
# <a name="how-to-add-a-biztalk-assembly-to-an-application"></a>Cómo agregar un ensamblado de BizTalk a una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para agregar un ensamblado de BizTalk a una aplicación.  
  
 Al agregar el ensamblado de BizTalk a una aplicación, tenga en cuenta que los siguientes puntos son importantes:  
  
-   Si desea agregar un ensamblado y sobrescribir otro con el mismo identificador local único (LUID) que ya existe en la aplicación, especifique la opción de sobrescritura. Si no se especifica y ya existe en la aplicación un ensamblado con el mismo LUID que el ensamblado agregado, se produce un error en la operación de agregación. El LUID incluye el nombre de archivo del ensamblado, así como su versión, referencia cultural y token de clave pública. Puede ver los LUID para los artefactos de una aplicación mediante la [comando ListApp](../core/listapp-command.md).  
  
-   Si el ensamblado que está agregando tiene una dependencia en otro artefacto que no está incluido en la aplicación, se producirá un error en la operación de agregación.  
  
-   Al agregar un ensamblado de BizTalk, puede especificar una o varias de las siguientes opciones para la instalación del ensamblado a la caché de ensamblados global (GAC):  
  
    -   **Agregar a la caché global de ensamblados de agregar recursos (gacutil).** al seleccionar esta opción, el ensamblado se instala en la GAC del equipo local cuando se agrega el ensamblado a una aplicación mediante los procedimientos que se describen en este tema.  
  
    -   **Agregar a la caché de ensamblados global en la importación de archivo MSI (gacutil).** al seleccionar esta opción, si se ha exportado la aplicación a un archivo .msi y el archivo .msi se ha importado en un grupo de BizTalk, el ensamblado se instala en la GAC del equipo local como parte del proceso de importación.  
  
    -   **Agregar a la caché de ensamblados global en la instalación de archivos MSI (gacutil).** Al seleccionar esta opción, si se ha exportado la aplicación a un archivo .msi y se ha instalado la aplicación en un equipo desde el archivo .msi, el ensamblado se instala en la GAC del equipo local como parte del proceso de instalación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-add-a-biztalk-assembly-to-an-application"></a>Para agregar un ensamblado de BizTalk a una aplicación  
  
#### <a name="using-the-biztalk-server-administration-console"></a>Mediante la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda Administración de BizTalk Server y el grupo de BizTalk que contiene la aplicación a la que desea agregar el ensamblado de BizTalk.  
  
3.  Expanda Administración de la aplicación la aplicación a la que desea agregar un ensamblado de BizTalk.  
  
4.  Haga clic en **recursos**, seleccione **agregar** y, a continuación, haga clic en **ensamblados de BizTalk**.  
  
5.  Haga clic en **agregar**, seleccione el archivo de ensamblado de BizTalk y, a continuación, haga clic en **abiertos**.  
  
6.  En **destino**, escriba la ruta de acceso completa de la ubicación donde el archivo de ensamblado se va a copiar cuando la aplicación se instala desde el archivo .msi, incluido el nombre de archivo. Si no se proporciona, el archivo de ensamblado no se copia al sistema de archivos local durante instalación.  
  
7.  En **opciones**, especifique las opciones para instalar el ensamblado de BizTalk en la GAC y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="using-the-command-line"></a>Utilizar la línea de comandos  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask AddResource** [**/ApplicationName:***valor*] **/Type:System.BizTalk:BizTalkAssembly** [**/Overwrite**] **/Source:***valor* [**/Destination:***valor*] [**/Options:GacOnAdd**&#124; **GacOnInstall**&#124; **GacOnImport**] [**/Server:***valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:BizTalkAssembly / Overwrite/Source: "C:\BizTalk Assemblies\MyOrchestration.dll" /Destination: / Server "C:\New BizTalk Assemblies\ MyOrchestration.dll": MiServidorDeBasesDeDatos /Database:BizTalkMgmtDb**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega el ensamblado de BizTalk. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/ Tipo**|**System.BizTalk:BizTalkAssembly**|  
    |**/ Sobrescribir**|Opción para actualizar un ensamblado existente. Si no se especifica y ya existe un ensamblado en la aplicación que tiene el mismo LUID que el ensamblado que se agrega, se produce un error en la operación AddResource. Puede ver los LUID para los artefactos de una aplicación mediante la [comando ListApp](../core/listapp-command.md). Sin embargo, si otra aplicación depende del ensamblado que se está sobrescribiendo, se producirá un error en la operación AddResource aunque se especifique este parámetro.|  
    |**Código fuente**|Ruta de acceso completa al archivo de ensamblado, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
    |**/ Destino**|Ruta completa de la ubicación en la que se va a copiar el archivo de ensamblado cuando se instale la aplicación desde el archivo .msi. Si no se proporciona, el archivo de ensamblado no se copia al sistema de archivos local durante instalación. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
    |**/ Opciones**|-   **GacOnAdd**: especificar para instalar el ensamblado en la caché global de ensamblados (GAC) en el equipo local durante la operación AddResource.<br />-   **GacOnInstall**: Especifica que se instale el ensamblado a la GAC cuando se instala la aplicación desde el archivo MSI.<br />-   **GacOnImport**: Especifica que se instale el ensamblado a la GAC cuando se importa el archivo .msi de aplicación.<br /><br /> Debe separar varias opciones mediante una coma.|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar ensamblados de BizTalk](../core/managing-biztalk-assemblies.md)   
 [AddResource (comando): ensamblado de BizTalk](../core/addresource-command-biztalk-assembly.md)