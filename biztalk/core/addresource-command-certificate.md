---
title: 'AddResource (comando): Certificado | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e915043-6634-4644-8d69-376d762c7cec
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e6fc335b3765299ee1b26b40d235e55240a2b53
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984949"
---
# <a name="addresource-command-certificate"></a>AddResource (comando): certificado
Para agregar un certificado de seguridad a una aplicación de BizTalk, usa el **AddResource** comando y especifique **BizTalk: Certificate** para el parámetro de tipo. Para que funcione este comando, el certificado debe estar presente en el almacén de certificados Otras personas del equipo local.  
  
 Ejecutar este comando agrega el certificado a la base de datos de administración de BizTalk. Además, el certificado aparece en la consola de administración de BizTalk Server en la carpeta Recursos de la aplicación a la que lo agregó. Además, el certificado se enumera cuando se utiliza el [comando ListApp](../core/listapp-command.md).  
  
 Cuando instala la aplicación, el certificado se importa al almacén de certificados Otras personas del equipo local.  
  
## <a name="usage"></a>Uso  
 **BTSTask AddResource** [**/ApplicationName:**<em>valor</em>] **/Type:System.BizTalk:Certificate** [**/Overwrite**] **/Thumbprint: "**<em>valor</em>**"** [**/Server:**<em>valor</em>] [**/ Base de datos:**<em>valor</em>]  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Valor|  
|---------------|--------------|-----------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|no|Nombre de la aplicación de BizTalk a la que se agrega el certificado. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles ("). Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo.|  
|**/ Escriba** (o **/Ty**, vea la sección Comentarios)|Sí|**BizTalk: Certificate** (este valor no distingue mayúsculas de minúsculas).|  
|**/ Sobrescribir** (o **/O**, vea la sección Comentarios)|no|Opción para actualizar un certificado existente. Si no se especifica y ya existe un certificado en la aplicación que tiene la misma propiedad Huella digital que el certificado que se agrega, se produce un error en la operación Agregar. Puede ver la propiedad Huella digital si hace doble clic en el certificado del complemento Certificados y si hace clic en la pestaña Detalles. Para obtener más información, consulte la sección acerca de información de certificado de la documentación del complemento Certificados.|  
|**/ Huella digital** (o **/Th**, vea la sección Comentarios)|Sí|Propiedad de huella digital del certificado (una *huella digital* es una síntesis de datos). Este valor se debe incluir entre comillas dobles (").|  
|**/ Servidor** (o **/S**, vea la sección Comentarios)|no|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
|**/ Base de datos** (o **/D**, vea la sección Comentarios)|no|Nombre de la base de datos de administración de BizTalk. Si no se proporciona, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="sample"></a>Ejemplo  
 **/ApplicationName:MyApplication BTSTask AddResource/Type: BizTalk: Certificate sobrescribir /Thumbprint: "04 8e a2 32 24 f9 a 36 b9 42 81 12 71 3a d2 ef db c7 9C 83 dc" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>Notas  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [AddResource (comando)](../core/addresource-command.md)   
 [Cómo agregar un certificado a una aplicación](../core/how-to-add-a-certificate-to-an-application.md)