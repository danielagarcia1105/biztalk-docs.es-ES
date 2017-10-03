---
title: Comando ExportParties | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b421c8ed-d505-48ba-9d1d-8519c9d51750
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca525872ccc1cd941673189c4ac176fc4631f22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="exportparties-command"></a>Comando ExportParties
Exporta todas las entidades y los contratos a un archivo de enlaces XML.

> [!IMPORTANT]
> Este comando es nuevo a partir de  **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** y las versiones más recientes.

## <a name="usage"></a>Uso
  **BTSTask ExportParties-destino**:*valor* [**-Server**:*valor*] [**-base de datos**: *valor*]
  
## <a name="parameters"></a>Parámetros

|Parámetro|Necesario|Valor|  
|---|---|---|  
| **: Destino** | Necesario | Ruta de acceso y el nombre del archivo de enlace XML que se escribirá. |
| **-Servidor** | Opcional | El nombre de SQL server que hospeda la base de datos de configuración de BizTalk. |
| **-Base de datos** | Opcional | Nombre de la base de datos de configuración de BizTalk.|

## <a name="sample"></a>Ejemplo
  `ExportParties  -Destination:"C:\Temp\MyParties.Xml"` 

## <a name="remarks"></a>Comentarios
  Se exporta solo entidades, acuerdos y configuración de reserva de EDI. No hay artefactos de la aplicación se exportan.
