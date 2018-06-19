---
title: Cómo agregar un directorio Virtual para una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directories
- managing [applications], virtual directories
- applications, virtual directories
- virtual directories, applications
ms.assetid: a5726696-bd65-49d9-8814-a078afe8c067
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26627387a65b19cef8146cee8b91b2a7a0919059
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248884"
---
# <a name="how-to-add-a-virtual-directory-to-an-application"></a>Cómo agregar un directorio virtual a una aplicación
En este tema se describe cómo usar la herramienta de línea de comandos BTSTask para agregar un directorio virtual a una aplicación de BizTalk. Esta opción no está disponible en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede que desee agregar un directorio virtual si ha escrito un servicio web personalizado o si ha creado un sitio web ASP.NET para interactuar con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y desea implementar el directorio virtual con la aplicación.  
  
 Otra manera de agregar un directorio virtual para una aplicación es mediante la especificación de un directorio virtual para un SOAP o HTTP ubicación de recepción, como se describe en [cómo configurar una ubicación de recepción HTTP](../core/how-to-configure-an-http-receive-location.md). En todos los casos, el directorio virtual se agrega a la base de datos de administración de BizTalk. Cuando se agrega un directorio virtual mediante el uso de la línea de comandos, también se muestra en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la carpeta de recursos de la aplicación a la que se agregó, así como la lista de artefactos de la aplicación cuando se usa el [Comando ListApp](../core/listapp-command.md). Si posteriormente exporta la aplicación y, a continuación, la importa en otro grupo de BizTalk, el directorio virtual se muestra en la carpeta Recursos.  
  
 Al agregar un directorio virtual a una aplicación, tenga en cuenta los siguientes puntos:  
  
-   Puede sobrescribir un directorio virtual que exista ya en la aplicación, especificando la opción de sobrescritura. La opción de sobrescritura es necesaria sólo cuando el directorio virtual existente tiene el mismo nombre que el que desea agregar. Si no se especifica y un directorio virtual ya existe en la aplicación con el mismo nombre que el que se agrega, se producirá un error en la operación de agregación.  
  
-   Al agregar un directorio virtual con una dirección URL que contiene https, debe utilizar http en lugar de https en la dirección URL que especifica. Si utiliza https, se producirá un error en la operación de agregación de un directorio virtual. Aunque lo agregue con http en la dirección URL, la configuración https para la dirección URL en la metabase de Internet Information Services tendrá efecto y el directorio virtual funcionará correctamente.  
  
-   Si agrega un directorio virtual desde una versión de 64 bits del servicio Web e intenta instalar la aplicación que incluye el directorio virtual en un equipo de 32 bits, no se instalará el directorio virtual. Debe estar instalado en un equipo de 64 bits.  
  
> [!IMPORTANT]
>  Al importar una aplicación que contiene un directorio virtual, la configuración de seguridad del directorio virtual es la que está activa cuando el archivo .msi se genera durante la exportación de la aplicación. Si implementa una aplicación en un entorno de producción, antes de exportar la aplicación debería comprobar que la configuración satisface los requisitos de seguridad.  
>   
>  Si, en cambio, el directorio virtual ya existe en el entorno de destino, estará activa la configuración de seguridad del directorio virtual existente. No se modifica para que coincida con la del directorio virtual que va a implementar. En este caso, debería comprobar que la configuración de seguridad del directorio virtual existente cumple con los requisitos que desea.  
  
> [!CAUTION]
>  Si el directorio virtual usa el protocolo HTTPS (Protocolo de transferencia de hipertexto a través de capa de sockets seguros), la configuración de seguridad no se mantiene durante la exportación y cuando se importa, el directorio virtual heredará la configuración de seguridad del elemento raíz. Debería comprobar que la configuración de seguridad cumple con los requisitos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe haber iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-add-a-virtual-directory-to-an-application"></a>Para agregar un directorio virtual a una aplicación  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask AddResource** [/**ApplicationName:***valor*] **/Type:System.BizTalk:WebDirectory**[**/Overwrite**] **/Source:***valor* [**/Destination:***valor*] [**/Server:**  *valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **Tipo de BTSTask AddResource /ApplicationName:MyApplication /: System.BizTalk:WebDirectory / Overwrite /Source:http://Host1:90 / MyVirtualDirectory /Destination:http://Host2:90 / MyVirtualDirectory /Server:MyDatabaseServer /Database: BizTalkMgmtDb**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega el directorio virtual. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/ Tipo**|**System.BizTalk:WebDirectory** (este valor no distingue entre mayúsculas y minúsculas).|  
    |**/ Sobrescribir**|Opción para actualizar un directorio virtual existente. Si no se especifica y ya existe un directorio virtual en la aplicación que tiene el mismo nombre que el directorio virtual que se agrega, se produce un error en la operación AddResources.|  
    |**Código fuente**|URI del directorio virtual de origen.|  
    |**/ Destino**|URI que se va a asignar al directorio virtual cuando se desinstale la aplicación del archivo .msi. Si no se especifica este parámetro, se utiliza el valor del parámetro Source teniendo localhost como host.|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource (comando): Directorio Virtual](../core/addresource-command-virtual-directory.md)   
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)