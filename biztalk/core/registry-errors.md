---
title: Errores del registro | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a5bf2cd-f807-4083-8687-4416a2ee2908
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62522299866748d92abf91d36a01444c3175b070
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975117"
---
# <a name="registry-errors"></a>Errores de Registro
Información para diagnosticar y resolver errores del registro de WCF.  

## <a name="failed-to-access-the-registry"></a>Error al obtener acceso al Registro
  
|                 |                                   Detalles del error                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                             No se pudo abrir HKLM\\{0}.                              |
  
### <a name="explanation"></a>Explicación  
 Este error indica un error al obtener acceso al Registro.  
  
### <a name="user-action"></a>Acción del usuario  
 Asegúrese de tener acceso de lectura para el Registro. Para obtener acceso al Registro, asegúrese de que tiene privilegios de Administrador o póngase en contacto con el administrador del equipo.
 
## <a name="failed-to-obtain-biztalk-install-path"></a>No se pudo obtener la ruta de instalación de BizTalk
  
|                 |                                   Detalles del error                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |             No se pudo obtener la ruta de instalación de BizTalk de HKLM\\{0}\\{1}              |
  
## <a name="explanation"></a>Explicación  
 Este mensaje indica un error al obtener acceso al Registro y que la clave tiene un valor incorrecto.  
  
## <a name="user-action"></a>Acción del usuario  
 Asegúrese de tener acceso de lectura para el Registro. Asegúrese de que la clave tenga el valor correcto. Para obtener acceso al Registro, asegúrese de que tiene privilegios de Administrador o póngase en contacto con el administrador del equipo. 