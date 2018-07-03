---
title: 'De sesión único: Evento 10757 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24765a25-560b-4391-9839-a325894c679f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08a75a95a3804ee429baaf24c6b89bbb68a0ce6a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008149"
---
# <a name="single-sign-on-event-10757"></a>De sesión único: Evento 10757
## <a name="details"></a>Detalles  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                  Inicio de sesión único (SSO) empresarial                                   |
| Versión del producto |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    Identificador del evento     |                                            10757                                             |
|  Origen del evento   |                                            ENTSSO                                            |
|    Componente    |                                             N/D                                              |
|  Nombre simbólico  |                                     ENTSSO_E_NO_MAPPING                                      |
|  Texto del mensaje   | La asignación no existe. No se estableció la información de configuración para aplicaciones de almacén de configuración. |
  
## <a name="explanation"></a>Explicación  
 Si se trata de una aplicación del tipo "Individual" o "Grupo", la asignación no existe.  
  
 Si se trata de una aplicación de almacén de configuración, no se establecieron los datos de configuración. Esto puede ocurrir cuando se ha vuelto a inicializar la base de datos de SSO pero no la base de datos de administración de BizTalk o viceversa.  
  
## <a name="user-action"></a>Acción del usuario  
 Si se trata de una aplicación del tipo "Individual" o "Grupo", cree la asignación deseada. Para obtener más información, consulte [cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md).