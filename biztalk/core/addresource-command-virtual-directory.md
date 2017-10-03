---
title: 'Comando AddResource: Directorio Virtual | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 446be3b3-31da-4f03-81b5-3a75c8da6558
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f28605a4bac678cefaafcb853d3dcdc55994831
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command-virtual-directory"></a>AddResource (comando): Directorio Virtual
Para agregar un directorio virtual para un sitio Web o servicios Web a una aplicación de BizTalk, use la **AddResource** comando y especifique **System.BizTalk:WebDirectory** para el parámetro de tipo. Ejecutar este comando agrega el directorio virtual a la base de datos de administración de BizTalk. También se muestra el directorio virtual en la consola de administración de BizTalk Server, en la carpeta Recursos de la aplicación a la que lo agregó. Además, el directorio virtual se enumera cuando se utiliza el [comando ListApp](../core/listapp-command.md).  
  
> [!IMPORTANT]
>  Al agregar un directorio virtual con una dirección URL que contiene https, debe utilizar http en lugar de https en la dirección URL que especifica. Si utiliza https, se producirá un error en la operación de agregación de un directorio virtual. Aunque lo agregue con http en la dirección URL, la configuración https para la dirección URL en la metabase de Internet Information Services tendrá efecto y el directorio virtual funcionará correctamente.  
  
> [!NOTE]
>  Si agrega un directorio virtual desde una versión de 64 bits del servicio Web e intenta instalar la aplicación que incluye el directorio virtual en un equipo de 32 bits, no se instalará el directorio virtual. Se instalará sólo en un equipo de 64 bits.  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [/**ApplicationName:***valor*] **/Type:System.BizTalk:WebDirectory**[**/Overwrite**] **/Source:***valor* [**/Destination:***valor*] [**/Server:**  *valor*] [**/Database:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|No|Nombre de la aplicación de BizTalk a la que se agrega el directorio virtual. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**System.BizTalk:WebDirectory** (este valor no distingue entre mayúsculas y minúsculas).|  
|**/ Sobrescribir** (o **/o**, vea la sección Comentarios)|No|Opción para actualizar un directorio virtual existente. Si no se especifica y ya existe un directorio virtual en la aplicación que tiene el mismo nombre completo que el directorio virtual que se agrega, se produce un error en la operación AddResource.|  
|**/ Origen** (o **/S**, vea la sección Comentarios)|Sí|URI completo del directorio virtual de origen.<br /><br /> Ejemplos:<br /><br /> http://MyHost:80/MyPath/MyVirtualDirectory|  
|**/ Destino** (o **/De**, vea la sección Comentarios)|No|URI que se va a asignar al directorio virtual cuando se desinstale la aplicación del archivo .msi. Si no se especifica este parámetro, se utiliza el valor del parámetro Source teniendo localhost como host.|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **Tipo de BTSTask AddResource /ApplicationName:MyApplication /: System.BizTalk:WebDirectory / Overwrite /Source:http://Host1:90 / MyVirtualDirectory /Destination:http://Host2:90 / MyVirtualDirectory /Server:MyDatabaseServer /Database: BizTalkMgmtDb**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar un ensamblado de .NET a una aplicación](../core/how-to-add-a-net-assembly-to-an-application.md)