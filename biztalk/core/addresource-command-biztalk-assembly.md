---
title: 'AddResource (comando): El ensamblado de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c18607b5-d929-48c9-9fa3-f728a7a80d04
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21dcffc7a404f891dbcb01c7d84e0236106308e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011093"
---
# <a name="addresource-command-biztalk-assembly"></a>AddResource (comando): El ensamblado de BizTalk
Para agregar un ensamblado de BizTalk a una aplicación de BizTalk, usa el **AddResource** comando y especifique **System.BizTalk:BizTalkAssembly** para el parámetro de tipo. Ejecutar este comando agrega el ensamblado a la base de datos de administración de BizTalk. El ensamblado también se muestra en la consola de administración de BizTalk Server, en la carpeta de recursos de la aplicación a la que se agregó. Los artefactos incluidos en el ensamblado también se muestran en las carpetas correspondientes. Además, los artefactos se muestran cuando se usa el [comando ListApp](../core/listapp-command.md).  
  
 Cuando utilice este comando, tenga en cuenta los puntos siguientes:  
  
- Si un ensamblado tiene el mismo nombre completo que un ensamblado ya existente en la aplicación, debe especificar el parámetro Overwrite ya que de no ser así, se producirá un error en la operación AddResource. El nombre completo consta del nombre, del token de clave pública, de la referencia cultural y de la versión. Sin embargo, si otra aplicación depende de este ensamblado, se producirá un error en la operación AddResource aunque especifique el parámetro Overwrite.  
  
- Si existe otro ensamblado que tiene el mismo nombre completo en el grupo, se producirá un error en la operación AddResource aunque especifique el parámetro Overwrite.  
  
- Si está sobrescribiendo un ensamblado que contiene orquestaciones, las orquestaciones se deben detener y dar de baja antes de ejecutar este comando. Asimismo, se deben detener y dar de baja los puertos de envío a los que está enlazada la orquestación y se deben deshabilitar las ubicaciones de recepción.  
  
- Si el ensamblado que está agregando tiene una dependencia en otro artefacto que no está incluido en la aplicación, se producirá un error en la operación AddResource.  
  
  Para obtener más información acerca de las dependencias, consulte [dependencias e implementación de aplicación](../core/dependencies-and-application-deployment.md).  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName:**<em>valor</em>] **/Type:System.BizTalk:BizTalkAssembly** [**/Overwrite**] **/Source:**<em>valor</em> [**/Destination:**<em>valor</em>] [**/Options:GacOnAdd** <em>&#124;</em> **GacOnInstall**<em>&#124;</em>**GacOnImport**] [**/Server:**  <em>valor</em>] [**/Database:**<em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|no|Nombre de la aplicación de BizTalk a la que se agrega el ensamblado. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**System.BizTalk:BizTalkAssembly** (este valor no distingue mayúsculas de minúsculas).|  
|**/ Sobrescribir** (o **/Ov**, vea la sección Comentarios)|no|Opción para actualizar un ensamblado existente. Si no se especifica y ya existe un ensamblado en la aplicación que tiene el mismo nombre completo que el ensamblado que se agrega, se produce un error en la operación AddResource. El nombre completo corresponde con el identificador local único (LUID) para el ensamblado. Puede ver los LUID para los artefactos de una aplicación mediante el uso de la [comando ListApp](../core/listapp-command.md). Sin embargo, si otra aplicación depende del ensamblado que se está sobrescribiendo, se producirá un error en la operación AddResource aunque se especifique este parámetro.|  
|**/ Origen** (o **/So**, vea la sección Comentarios)|Sí|Ruta de acceso completa del archivo de ensamblado, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
|**/ Destino** (o **/De**, vea la sección Comentarios)|no|Ruta completa de la ubicación en la que se va a copiar el archivo de ensamblado cuando se instale la aplicación desde el archivo .msi. Si no se proporciona, el archivo de ensamblado no se copia al sistema de archivos local durante instalación. Si la ruta incluye espacios, la debe encerrar entre comillas dobles ("). **Nota:** entorno variable % BTAD_InstallDir %, que se establece durante la instalación de BizTalk Server, puede usar para especificar la carpeta de instalación de la aplicación. Esto creará una ubicación coherente para los archivos de la aplicación en equipos de destino diferentes. Ejemplo: "% BTAD_InstallDir%\MyFiles\Orchestrations.dll"|  
|**/ Las opciones** (o **/op.**, vea la sección Comentarios)|no|-   **GacOnAdd**: especificar para instalar el ensamblado en la caché global de ensamblados (GAC) en el equipo local durante la operación AddResource.<br />-   **GacOnInstall**: Especifica que se instale el ensamblado a la GAC cuando se instala la aplicación desde el archivo MSI.<br />-   **GacOnImport**: Especifica que se instale el ensamblado a la GAC cuando se importa el archivo .msi de aplicación.<br /><br /> Debe separar varias opciones mediante una coma.|  
|**/ Servidor** (o **/Se**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:BizTalkAssembly / Overwrite**  
  
 **/Options:GacOnInstall /Source:"%BTAD_InstallDir%\Source Assemblies\Orchestrations.dll" /Destination:"%BTAD_InstallDir%\New Assemblies\Orchestrations.dll", GacOnImport /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md)