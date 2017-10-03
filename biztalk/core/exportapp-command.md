---
title: Comando ExportApp | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6217d0f1-cf39-4520-87c8-8d25b21865af
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 966e53a7c74ce687724a77ea57888a4c61bb2773
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="exportapp-command"></a>ExportApp (comando)
Exporta una aplicación de BizTalk a un archivo .msi. Si existe un archivo .msi que ya tiene el mismo nombre de archivo y ruta de acceso, se sobrescribe el archivo existente .msi.  
  
 Puede utilizar el parámetro ResourceSpec para exportar selectivamente los artefactos de una aplicación a un archivo .msi. Especificar qué artefactos se van a exportar, edite el archivo XML crean cuando ejecuta el **ListApp** comando con el parámetro ResourceSpec, como se describe en [comando ListApp](../core/listapp-command.md). Utilizar, a continuación, la ubicación de este archivo XML como el valor de ResourceSpec cuando se ejecuta el **ExportApp** comando. Al hacerlo, solo se exportan al archivo .msi los artefactos que aparecen en el archivo XML especificado.  
  
> [!NOTE]
>  Por motivos de seguridad, las contraseñas se quitan de los enlaces de aplicación durante la exportación de la aplicación. No se quitan de ningún archivo de enlace que se haya agregado a la aplicación. Después de instalar la aplicación desde el archivo .msi, debe volver a configurar las contraseñas para que funcione la aplicación.  
>   
>  Asimismo, las claves privadas se quitan de los archivos de certificado.  
  
## <a name="usage"></a>Uso  
 **ExportApp de BTSTask** [**/ApplicationName:***valor*] **/paquete:***valor* [**/ ResourceSpec:***valor*] [**/GlobalParties**] [**/Server:***valor*] [**/ Base de datos:***valor*]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|No|Nombre de la aplicación de BizTalk que se va a exportar. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo.|  
|**/ Paquete** (o **/P**, vea la sección Comentarios)|Sí|Ruta completa del archivo .msi. Si la ruta de acceso incluye espacios, debe encerrarlo entre comillas ("). Ejemplo: Paquete: "C:\My MSI Files\My.msi"|  
|**/ ResourceSpec** (o **/r**, vea la sección Comentarios)|No|Ruta de acceso completa del archivo de especificación del recurso. Si la ruta de acceso incluye espacios, debe encerrarlo entre comillas ("). Ejemplo: ResourceSpec: "C:\My Files\MyResourceSpec.xml"|  
|**/ GlobalParties** (o **/G**, vea la sección Comentarios)|No|Si se especifica, la información de entidad global del grupo se exporta en el archivo .msi.|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|No|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/D**, vea la sección Comentarios)|No|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **ExportApp /ApplicationName:MyApplication /Package:C:\MSI\MyApplication.msi**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
 [Cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md)