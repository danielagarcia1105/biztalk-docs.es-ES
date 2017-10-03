---
title: Comando ImportSettings | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 587f7e1f-9cf7-4e7b-90cd-11a266f474dc
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c609634422f8c8b5f2c1a96691fe4eda708e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importsettings-command"></a>Comando ImportSettings
Importa la configuración de grupo, host o instancia de host de BizTalk desde un archivo XML de origen a la base de datos de configuración. La configuración se asigna tal como está en el archivo XML de asignación. Estas opciones se pueden haber exportado tal y como se describe en [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) o [importación o exportación BTSTask de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-btstask.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar esta operación, debe iniciar sesión como miembro del grupo Administradores de BizTalk Server.  
  
## <a name="usage"></a>Uso  
 `ImportSettings –Source:value –Map: value [-Server:value] [-Database:value]`  
  
## <a name="parameters"></a>Parámetros  
  
|**Parámetro**|Necesario|Valor|  
|-------------------|--------------|-----------|  
|**-Origen**|Sí|Ruta de acceso y el nombre del archivo XML de configuración exportado.|  
|**-Mapa**|Sí|Ruta de acceso y el nombre del archivo XML de asignación.|  
|**-Servidor**|Opcional|El nombre del equipo SQL Server que hospeda la base de datos de configuración de BizTalk.|  
|**-Base de datos**|Opcional|Nombre de la base de datos de configuración de BizTalk.|  
  
## <a name="sample"></a>Ejemplo  
 `BTSTask ImportSettings /Source:”C:\My Folder>\ExportedSettings.xml” /Map:Mappings.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros no distinguen mayúsculas de minúsculas. No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)