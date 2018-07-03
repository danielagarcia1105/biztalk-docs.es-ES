---
title: Errores en los metadatos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccb60c91-5905-4852-813b-586b82de4825
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07167c2c0189c36f7b1a321d81bd0070398953e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975125"
---
# <a name="metadata-errors"></a>Errores de metadatos
Información para diagnosticar y resolver errores en los metadatos de WCF.  
  
## <a name="error-consuming-wcf-service-metadata"></a>Error al consumir los metadatos del Servicio WCF

|                 |                                   Detalles del error                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                        Error al consumir los metadatos del Servicio WCF                        |
  
### <a name="explanation"></a>Explicación  
 Este error indica que los metadatos para el servicio no están disponibles o que no son válidos.  
  
### <a name="user-action"></a>Acción del usuario  
 Corrija los metadatos del servicio e intente consumirlo (si es propietario del Servicio WCF que está intentando consumir). Vaya al Editor de configuración de servicio (**svcConfigEditor.exe**) y realizar cambios en el archivo de configuración.  En caso contrario, póngase en contacto con el proveedor de servicios

## <a name="failed-to-get-metadata"></a>Error al obtener metadatos

|                 |                                   Detalles del error                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                          Error al obtener los metadatos de"{0}                          |
  
## <a name="explanation"></a>Explicación  
 Este error indica que los metadatos no están disponibles para el servicio.  
  
## <a name="user-action"></a>Acción del usuario  
 Habilite los metadatos para el servicio y vuelva a ejecutar el Asistente para consumición (si es propietario del Servicio WCF que intenta consumir). En caso contrario, póngase en contacto con el proveedor de servicios.