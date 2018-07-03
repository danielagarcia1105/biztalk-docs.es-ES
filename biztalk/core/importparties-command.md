---
title: ImportParties (comando) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d43e2c-401c-4450-ad9b-2528086b99e4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c25b913b6479b857fb7cee4aec10e6984f2195
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998541"
---
# <a name="importparties-command"></a>ImportParties (comando)
Importa las entidades de negocio a negocio y los contratos desde un archivo de enlace XML de origen en la base de datos de configuración, sin incluir ningún artefacto de la aplicación. Para obtener más información, consulte **comentarios** en este tema.  

> [!IMPORTANT]
> Este comando es nuevo a partir de **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** y las versiones más recientes.
> 
> [!NOTE]
>  Enlace los archivos generados en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no tiene una aplicación especificada. Se importan a la aplicación predeterminada.  
  
## <a name="usage"></a>Uso  
  **BTSTask ImportParties-origen**:*valor* [**- ExcludeEdiFallbackSettings**] [**-Server**:*valor*] [**-Base de datos**:*valor*]
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Obligatorio|Valor|  
|---|---|---|  
|**: Origen** | Obligatorio | La ruta de acceso y el nombre del archivo de enlace XML para leer.|
|**-ExcludeEdiFallbackSettings** | Opcional | Si se especifica, excluye la configuración de (x12 y edifact) reserva edi desde el archivo de enlace.  |
| **-Servidor** | Opcional | El nombre de SQL server que hospeda la base de datos de configuración de BizTalk. |
| **-Base de datos** | Opcional | Nombre de la base de datos de configuración de BizTalk. |

## <a name="sample"></a>Ejemplo
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a>Notas
Si el archivo de enlace también tiene artefactos de la aplicación, a continuación, no se importan. Se importan solo entidades y acuerdos.