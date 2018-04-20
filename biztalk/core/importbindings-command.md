---
title: Comando ImportBindings | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b8dd1ee-1719-4cd1-b503-b004f312daeb
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 576f9055e7b70ab43cc150f208f8c55789f28da8
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="importbindings-command"></a>ImportBindings (comando)
Importa enlaces desde un archivo de enlace basado en XML a un grupo o a una aplicación de BizTalk. Los enlaces pueden haber exportado de un ensamblado, la aplicación o el grupo, como se describe en [exportar enlaces](../core/exporting-bindings6.md). En función de la ubicación desde la que se exportaron los enlaces, los parámetros ApplicationName y GroupLevel tienen efectos diferentes. Para obtener más información, vea la sección "Comentarios" más adelante en este tema.  
  
> [!NOTE]
>  Enlace de archivos que se generan en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no tiene una aplicación especificada. Se importan a la aplicación predeterminada.  
  
## <a name="usage"></a>Uso  
 **BTSTask ImportBindings-origen**:*valor* [**- GroupLevel** &#124; **- ApplicationName**:*valor*] [**-Server**:*valor*] [**-base de datos**:*valor*] [**- ImportTrackingSettings**: *valor*] [**- ExcludeParties**]
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Value|  
|---------------|--------------|-----------|  
|**-Origen** (o **-tan**, vea la sección Comentarios)|Obligatorio|Ruta completa del archivo de enlace que se va a importar, incluido el nombre de archivo. Si el nombre de las rutas incluye espacios, debe ir entre comillas dobles (").|  
|**-GroupLevel** (o **- G**, vea la sección Comentarios)|Opcional|Opción para importar el archivo de enlace al grupo actual. Si especifica este parámetro, no especifique /ApplicationName.|  
|**-ApplicationName** (o **- A**, vea la sección Comentarios)|Opcional|Nombre de la aplicación de BizTalk en la que se van a importar los enlaces. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). La aplicación debe existir o se producirá un error en la operación de importación. Si no se especifica este parámetro, se utiliza la aplicación de BizTalk predeterminada. Si especifica este parámetro, no especifique /GroupLevel.|  
|**-Server** (o **-Se**, vea la sección Comentarios)|Opcional|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**-Base de datos** (o **-D**, vea la sección Comentarios)|Opcional|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
| **-ImportTrackingSettings** | Opcional | Nuevo a partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]. <br /><br />Esto invalida la opción de importación de configuración de seguimiento global. Un valor "true" permite la importación de la configuración del seguimiento. False no permite la importación de configuración de seguimiento. |
| **-ExcludeParties** | Opcional | Nuevo a partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]. <br /><br />Si se especifica, excluye la información de entidades desde el archivo de enlace. |
  
## <a name="sample"></a>Ejemplo  
 El comando siguiente importa enlaces a la aplicación denominada MyApplication del grupo predeterminado de BizTalk.  
  
`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml`
  
 El comando siguiente importa enlaces al grupo definido en la base de datos de administración de BizTalk que se ejecuta en una instancia del servidor SQL Server denominada MY_Server.  
  
 `BTSTask ImportBindings -GroupLevel -Server:MY_Server -Database:BiztalkMgmtDb -Source:C:\Bindings\Binding1.xml`
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
 Los enlaces se pueden haber exportado de un ensamblado, una aplicación o un grupo. En función de la ubicación desde la que se exportaron los enlaces, los parámetros ApplicationName y GroupLevel tienen efectos diferentes, como se muestra en la tabla siguiente.  
  
|Origen de los enlaces|Efecto con el parámetro ApplicationName|Efecto con el parámetro GroupLevel|  
|----------------------------|-----------------------------------------------|------------------------------------------|  
|Enlaces exportados de un ensamblado|La aplicación especificada en ApplicationName debe contener un ensamblado que tenga el mismo nombre que el ensamblado desde el que se exportó el archivo de enlace. De lo contrario, se produce un error en la operación de importación.|El grupo actual debe contener un ensamblado y una aplicación que tengan el mismo nombre que el ensamblado y la aplicación desde los que se exportó el archivo de enlace. De lo contrario, se produce un error en la importación.|  
|Enlaces exportados de una aplicación|La aplicación desde la que se exportó el archivo de enlace debe tener el mismo nombre que la aplicación especificada mediante ApplicationName. De lo contrario, se produce un error en la operación de importación.|La aplicación desde la que se exportó el archivo de enlace debe tener el mismo nombre que una aplicación del grupo al que se importan los enlaces. De lo contrario, se produce un error en la operación de importación.|  
|Enlaces exportados de un grupo|El grupo desde el que se exportó el archivo de enlace debe incluir una aplicación que tenga el mismo nombre que la aplicación especificada mediante ApplicationName. De lo contrario, se produce un error en la operación de importación.|Los enlaces se importan para las aplicaciones correspondientes. En otras palabras, los enlaces de una aplicación del grupo desde el que se exportaron los enlaces se importan a una aplicación que tiene el mismo nombre en el grupo actual.|  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
 [Cómo importar enlaces a un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md)   
 [Cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md)