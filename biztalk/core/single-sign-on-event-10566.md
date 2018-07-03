---
title: 'De sesión único: Evento 10566 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd140b-5503-40f8-bf5d-604fa763989e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4748670e128b5b3a9717e2e430acb976da7bb4d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015093"
---
# <a name="single-sign-on-event-10566"></a>De sesión único: Evento 10566
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                     Inicio de sesión único (SSO) empresarial                                                                      |
| Versión del producto |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    Identificador del evento     |                                                                               10566                                                                                |
|  Origen del evento   |                                                                               ENTSSO                                                                               |
|    Componente    |                                                                                N/D                                                                                 |
|  Nombre simbólico  |                                                                  SSO_WARN_CANNOT_UPDATE_APP_FLAGS                                                                  |
|  Texto del mensaje   | No se pueden actualizar algunos de los marcadores especificados para la aplicación. Se ignorarán.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Especifica la máscara de marca: %2 |
  
## <a name="explanation"></a>Explicación  
 No se pueden cambiar determinados marcadores en una aplicación. (Por ejemplo, no se permite cambiar el tipo de aplicación de Individual a Grupo). Los marcadores de esta aplicación se especifican en el texto de la advertencia.  
  
## <a name="user-action"></a>Acción del usuario  
 No se requiere ninguna acción del usuario.