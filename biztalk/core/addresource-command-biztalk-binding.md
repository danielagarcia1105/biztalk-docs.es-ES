---
title: 'Comando AddResource: Enlace de BizTalk | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69c732d3-82c8-4615-b68f-ed29b54ebbf3
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00f9a5eac7d2c6f2be72ba78ee4c538ca505151e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="addresource-command-biztalk-binding"></a>El comando AddResource: Enlace de BizTalk
Para agregar un archivo de enlace a una aplicación de BizTalk, use la **AddResource** comando y especifique **BizTalk: biztalkbinding** para el **tipo** parámetro. Cuando agrega un archivo de enlace, puede especificar un entorno de implementación para él. Cuando importa posteriormente la aplicación, puede seleccionar este entorno de implementación para aplicar los enlaces. Puede agregar cualquier número de archivos de enlace a una aplicación de BizTalk, cada uno personalizado para un entorno de implementación diferente. Para agregar varios archivos de enlace, ejecute este comando para cada archivo que desee agregar.  
  
 Puede agregar un archivo de enlace que haya exportado de un ensamblado, la aplicación o el grupo, como se describe en [ExportBindings (comando)](../core/exportbindings-command.md)y, a continuación, utilice el comando AddResource para agregar el archivo de enlace a una aplicación.  
  
 Ejecutar este comando agrega el archivo de enlace a la base de datos de administración de BizTalk y el archivo se muestra en la carpeta Recursos de la aplicación. Además, el archivo aparece cuando se usa el [comando ListApp](../core/listapp-command.md). A diferencia de lo que ocurre al importar un archivo de enlace, agregar un archivo de enlace no cambia inmediatamente los enlaces existentes. Los enlaces no se aplican hasta que la aplicación se importe a otro grupo de BizTalk.  
  
 Cuando agrega un archivo de enlace, puede especificar el entorno de implementación mediante el parámetro opcional "TargetEnvironment" /Property. El valor puede ser cualquier cadena que represente el entorno de implementación en el que desea aplicar los enlaces en este archivo, como Prueba o Producción. Si no especifica un valor para el parámetro/Property, un valor de  **\<predeterminado\>**  se especifica automáticamente, y este archivo de enlace se aplicarán cada vez que se importe la aplicación.  
  
 Cuando importa una aplicación que incluye uno o varios archivos de enlace que ha agregado explícitamente de esta forma, puede seleccionar los archivos de enlace que se van a aplicar al especificar el valor del parámetro /Property. Los enlaces se aplican en la importación de la aplicación.  
  
 A medida que se aplican los enlaces durante el proceso de importación, los enlaces que ya se han aplicado se sobrescriben con enlaces nuevos que tienen el mismo nombre. Es decir, surtirá efecto el último enlace de un nombre concreto que se aplica. Téngalo en cuenta cuando utilice varios archivos de enlace. Si contienen entradas duplicadas, tendrá efecto el último enlace aplicado. Cuando importa una aplicación, los enlaces se aplican en el orden siguiente:  
  
1.  Los enlaces de la aplicación generados por BizTalk Server que no se agregaron explícitamente a la aplicación mediante un archivo de enlace, pero que el usuario seleccionó explícitamente para exportarlos al archivo .msi de la aplicación.  
  
2.  Los archivos de enlace que se han agregado explícitamente y que no tienen especificado un entorno de implementación de destino. Los enlaces de este conjunto no se aplican en ningún orden específico.  
  
3.  Los enlaces que se ha agregado explícitamente y que tienen un entorno de implementación de destino asociado que coincide con el entorno de implementación seleccionado para la importación de la aplicación. Los enlaces de este conjunto no se aplican en ningún orden específico.  
  
 Para obtener más información, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). Para obtener información general sobre el uso de archivos de enlace, vea [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName: "***valor***"**] **/Type:System.BizTalk:BizTalkBinding/Property: TargetEnvironment = "***valor***"** [**/Overwrite**] **/Source:***valor* [**/Server:***valor*] [**/Database:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|No|Nombre de la aplicación de BizTalk a la que se agrega el archivo de enlace. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk.|  
|**/ Escriba** (o **/T**, vea la sección Comentarios)|Sí|**BizTalk: biztalkbinding** (este valor no distingue entre mayúsculas y minúsculas).|  
|**/ Origen** (o **/So**, vea la sección Comentarios)|Sí|Ruta completa del archivo de enlace, incluido el nombre de archivo. Si la ruta incluye espacios, la debe encerrar entre comillas dobles (").|  
|**/Property:TargetEnvironment =** (o **/P:TargetEnvironment =**, vea la sección Comentarios)|No|Cadena que especifica el entorno de implementación de destino. Puede utilizar cualquier cadena, por ejemplo Producción. Ejemplo: **/Property:TargetEnvironment = "Producción"**<br /><br /> Si no se especifica, un valor de  **\<predeterminado\>**  se aplica automáticamente. El valor distingue mayúsculas de minúsculas. Si el valor incluye espacios, lo debe encerrar entre comillas dobles ("). La longitud máxima del valor del entorno es 128 caracteres.|  
|**/ Sobrescribir** (o **/Ov**, vea la sección Comentarios)|No|Opción para actualizar un archivo de enlace existente. Si no se especifica y ya existe un archivo de enlace en la aplicación que tiene el mismo nombre de archivo que el archivo que se agrega, se produce un error en la operación AddResource.|  
|**/ Servidor** (o **/Se**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/Da**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:BizTalkBinding /Property:TargetEnvironment = / Source de prueba: "C:\Binding Files\MyBinding.xml" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Comentarios  
 Los nombres de propiedades distinguen mayúsculas de minúsculas. Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar un archivo de enlace a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md)