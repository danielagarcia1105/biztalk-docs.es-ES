---
title: Comando ImportApp | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8ee5a78-1e8f-4290-b70a-36f2f888a1d6
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4200b5559ddfc12597c95d0e924a0159665f5f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importapp-command"></a>ImportApp (comando)
Importa los artefactos contenidos en un archivo .msi a una aplicación de BizTalk. Si la aplicación no existe, se creará.  
  
 Al importar una aplicación, puede utilizar el parámetro /Environment para especificar el entorno de desarrollo de destino para la aplicación, si ha agregado archivos de enlace a esta aplicación que se personaliza para un entorno de desarrollo determinado. Para obtener información general, vea [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md). Para obtener instrucciones sobre cómo agregar archivos de enlace, consulte [comando AddResource: enlace de BizTalk](../core/addresource-command-biztalk-binding.md).  
  
> [!NOTE]
>  Una operación de importación agotará el tiempo de espera si supera 3600 segundos de duración. Si está intentando importar un archivo .msi y la operación agota el tiempo de espera, debería dividir el contenido de la aplicación en más de un archivo .msi exportando de nuevo la aplicación y seleccionando un subconjunto de artefactos para exportarlos. Para obtener más información, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
 Si se produce un error en la importación, BTSTask devuelve el número de errores. La mayoría de las acciones realizadas durante la operación se deshacen, excepto las siguientes:  
  
-   No se deshacen las acciones realizadas por secuencias personalizadas de comandos. Puede escribir las secuencias de comandos para que se deshagan mediante la variable de entorno Eliminar.  
  
-   Si los ensamblados estuvieron instalados en la caché de ensamblados global (GAC), no se quitan.  
  
-   No se quitan las entradas realizadas en el Registro de Windows.  
  
 Si la importación se realiza correctamente, BTSTask devuelve "0".  
  
## <a name="usage"></a>Uso  
 **ImportApp /Package de BTSTask:** *valor* [**/Environment:***valor*] [**/ApplicationName:**  *valor*] [**/Overwrite**] [**/Server:***valor*] [**/Database:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Valor|  
|---------------|--------------|-----------|  
|**/ Paquete** (o **/P**, vea la sección Comentarios)|Sí|Ruta completa del archivo .msi. Si la ruta incluye espacios, la debe encerrar entre comillas dobles ("). Ejemplo: "C:\My MSI msi\miaplicación. msi"|  
|**/ Entorno** (o **/E**, vea la sección Comentarios)|No|El entorno de implementación de destino del archivo de enlace que se va a aplicar, como Prueba. Este es el valor que se especificó para el entorno de implementación de destino cuando se agregó a la aplicación el archivo de enlace. Cuando no se especifica, se aplican todos los enlaces que no tienen especificado un entorno.|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|No|Nombre de la aplicación de BizTalk a la que se importan los artefactos del archivo .msi. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica, se utiliza la aplicación predeterminada. Si la aplicación especificada no existe, se creará la aplicación.|  
|**/ Sobrescribir** (o **/o**, vea la sección Comentarios)|No|Opción para sobrescribir artefactos en la aplicación con artefactos del archivo .msi que tienen el mismo identificador local único (LUID). Puede ver los LUID de los artefactos de una aplicación mediante el uso de la [comando ListApp](../core/listapp-command.md). Si no se especifica esta opción y si hay uno o más artefactos en la aplicación que tienen el mismo LUID que los artefactos del archivo .msi, se produce un error en la importación.|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/D**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **BTSTask ImportApp /Package:C:\MSI\MyApplication.msi /Environment:Test /ApplicationName:MyApplication / Overwrite**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
 [Cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md)