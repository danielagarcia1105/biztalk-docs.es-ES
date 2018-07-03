---
title: 'De sesión único: Evento 11023 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feeb4ede-6045-46bf-9f2b-65062c583faa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cecf9536babaf2510444abade571149c5fc0e0a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991541"
---
# <a name="single-sign-on-event-11023"></a>De sesión único: Evento 11023
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                 Inicio de sesión único (SSO) empresarial                                                                                                                                  |
| Versión del producto |                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                 |
|    Identificador del evento     |                                                                                                                                           11023                                                                                                                                            |
|  Origen del evento   |                                                                                                                                           ENTSSO                                                                                                                                           |
|    Componente    |                                                                                                                                            N/D                                                                                                                                             |
|  Nombre simbólico  |                                                                                                                             SSO_WARN_WINDOWS_PASSWORD_DELETED                                                                                                                              |
|  Texto del mensaje   | Se eliminó una contraseña de Windows no válida en la base de datos de SSO para evitar el bloqueo de cuenta.%r<br /><br /> Use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3 |
  
## <a name="explanation"></a>Explicación  
 Se eliminó una contraseña de Windows no válida.  
  
## <a name="user-action"></a>Acción del usuario  
 Use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows. Para obtener más información, consulte [SSO utilizando](../core/using-sso.md).