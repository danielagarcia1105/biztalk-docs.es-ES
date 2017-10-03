---
title: Comando ExportSettings | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa34dab1-c854-473e-a693-43ba45624e16
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab8c39ef6903affbd2a1446bbde18a56e1a7778c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="exportsettings-command"></a>Comando ExportSettings
El comando ExportSettings permite exportar la configuración de BizTalk Server de la base de datos de configuración de BizTalk Server a un archivo XML. A continuación, puede importar esta configuración en otro entorno tal como se describe en [cómo importar configuración de BizTalk utilizando el panel de configuración](../core/how-to-import-biztalk-settings-using-settings-dashboard.md) o [cómo importar la configuración de BizTalk usando BTSTask](../core/how-to-import-biztalk-settings-using-btstask.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.  
  
## <a name="usage"></a>Uso  
 `ExportSettings –Destination:value[-Server:value] [-Database:value]`  
  
## <a name="parameters"></a>Parámetros  
  
|**Parámetro**|Necesario|Valor|  
|-------------------|--------------|-----------|  
|**: Destino**|Sí|Ruta de acceso y nombre de archivo del archivo XML que se va a escribir.|  
|**-Servidor**|Opcional|Nombre del SQL Server que hospeda la base de datos de configuración de BizTalk.|  
|**-Base de datos**|Opcional|Nombre de la base de datos de configuración de BizTalk.|  
  
## <a name="sample"></a>Ejemplo  
 `BTSTask ExportSettings /Destination:MyFile.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)