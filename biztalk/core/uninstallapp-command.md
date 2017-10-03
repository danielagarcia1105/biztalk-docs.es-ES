---
title: Comando UninstallApp | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f45c9530-8138-40f1-b279-1428c5a7fbbc
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea94335882ffbcf01b69c450ef4a5eb80ef4fa3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="uninstallapp-command"></a>UninstallApp (comando)
Desinstala una aplicación de BizTalk desde el equipo local y también quita la aplicación de la lista de programas en Agregar o quitar programas del Panel de control. Este comando tiene el mismo efecto que si se quita una aplicación mediante Agregar o quitar programas. Si se han instalado varios archivos .msi para esta aplicación, se desinstalan todos los elementos instalados por todos los archivos .msi.  
  
 El nombre de aplicación que especifica para este comando debe coincidir con el nombre de aplicación tal y como se muestra en Agregar o quitar programas. Si no está seguro de que el nombre de la aplicación, puede usar el **ListPackage** comando para obtenerlo, tal y como se describe en [comando ListPackage](../core/listpackage-command.md).  
  
> [!IMPORTANT]
>  Aunque es posible desinstalar una aplicación haciendo doble clic en el archivo .msi, no es compatible realizar esto. Se debe a que varios archivos .msi se pueden instalar para la misma aplicación y utilizar este método no desinstalará todos los elementos asociados a la aplicación.  
  
## <a name="usage"></a>Uso  
 **/ ApplicationName BTSTask UninstallApp:** *valor*  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Necesario|Description|  
|---------------|--------------|-----------------|  
|**/ ApplicationName** (o **/A**, vea la sección Comentarios)|Sí|Nombre de la aplicación de BizTalk que se va a desinstalar. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
  
## <a name="sample"></a>Ejemplo  
 **BTSTask UninstallApp /ApplicationName:MyApplication**  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
 [Cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md)