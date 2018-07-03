---
title: 'De sesión único: Evento 10767 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef5efc04-a0b5-4fc7-9d0e-f7aa9a9c413d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a14733abb624207704b304ef9718608c9df1c4bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977341"
---
# <a name="single-sign-on-event-10767"></a>De sesión único: Evento 10767
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                Inicio de sesión único (SSO) empresarial                                                |
| Versión del producto |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                |
|    Identificador del evento     |                                                          10767                                                          |
|  Origen del evento   |                                                         ENTSSO                                                          |
|    Componente    |                                                           N/D                                                           |
|  Nombre simbólico  |                                                 ENTSSO_E_NO_SSO_SERVER                                                  |
|  Texto del mensaje   | No se pudo establecer la conexión con el servidor de SSO ‘%1’. Compruebe si SSO está configurado y si el servicio SSO está en ejecución en ese servidor. |
  
## <a name="explanation"></a>Explicación  
 El cliente de ENTSSO no puede establecer la conexión con el servidor de ENTSSO.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe la conectividad de red y asegúrese de que el nombre de servidor esté escrito correctamente.