---
title: RemoveResource (comando) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e2c6046-43d4-4ac1-a1b1-3795b4e44038
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95b636083542bb1291cd10881bd74ca9d41c15b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976997"
---
# <a name="removeresource-command"></a>RemoveResource (comando)
Quita (elimina) un artefacto de la base de datos de administración de BizTalk. Ejecutar este comando no quita el artefacto de la caché de ensamblados global (GAC), del sistema de archivos, del almacén de certificados, de Internet Information Services o del Registro de Windows si existe en cualquiera de estas ubicaciones. No quita una definición de BAM de la base de datos de importación principal de BAM ni directivas de la base de datos del motor de reglas. Si ejecuta este comando para quitar un archivo de enlace, los enlaces no se modificarán. Solo se quita el archivo de enlace.  
  
 Puede utilizar este comando para quitar los tipos de artefactos siguientes:  
  
- Ensamblado .NET(System.BizTalk:Assembly)  
  
- Definición de BAM (System.BizTalk:Bam)  
  
- Ensamblado de BizTalk (System.BizTalk:BizTalkAssembly  
  
- Archivo de enlace de BizTalk (System.BizTalk:BizTalkBinding)  
  
- Certificado de seguridad (System.BizTalk:Certificate)  
  
- Componente COM (System.BizTalk:Com)  
  
- Archivo ad hoc (System.BizTalk:File)  
  
- Secuencia de comandos posterior al procesamiento (System.BizTalk:PostProcessingScript)  
  
- Secuencia de comandos previa al procesamiento (System.BizTalk:PreProcessingScript)  
  
- Directiva o regla (System.BizTalk:rules)  
  
- Directorio virtual (System.BizTalk:WebDirectory)  
  
  Se producirá un error en la operación de quitar cuando:  
  
- Intenta quitar un ensamblado de BizTalk del que tiene una referencia otro ensamblado.  
  
- Intenta quitar un ensamblado de BizTalk que incluye una canalización que utiliza el puerto de envío o recepción.  
  
- Intenta quitar un ensamblado de BizTalk que incluye una asignación que utiliza un puerto de envío.  
  
- Intenta quitar un ensamblado de BizTalk que incluye una orquestación que no está en un estado dado de baja o que tiene una instancia suspendida.  
  
## <a name="usage"></a>Uso  
 **/ ApplicationName BTSTask RemoveResource:** *valor* **/Luid:** *valor* [**/Server:**<em>valor</em> ] [**/Database:**<em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Descripción|  
|---------------|--------------|-----------------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|Sí|Nombre de la aplicación de BizTalk que contiene el artefacto de recurso que se va a eliminar. Si el nombre incluye espacios, debe encerrar entre comillas dobles (").|  
|**/ Luid** (o **/l**, vea la sección Comentarios)|Sí|Identificador local único (LUID) del artefacto. Puede obtener el LUID mediante el [comando ListApp](../core/listapp-command.md).|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/D**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, versión = 1.0.0.0, Culture = neutral, PublicKeyToken = 0123456789ABCDEF"**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
 [Cómo quitar un artefacto de una aplicación](../core/how-to-remove-an-artifact-from-an-application.md)