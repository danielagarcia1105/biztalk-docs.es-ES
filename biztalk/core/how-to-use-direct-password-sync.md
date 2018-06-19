---
title: Cómo usar la sincronización de contraseña directa | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1334c2f-2020-46ea-a98c-f7688813e38c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6080589271d845432e875cb335a2ef354c9784ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255948"
---
# <a name="how-to-use-direct-password-sync"></a>Cómo utilizar la sincronización directa de contraseñas
Esta versión del inicio de sesión único empresarial incluye la característica de sincronización directa de contraseña desde Windows. Esta característica le permite evitar el uso del adaptador de sincronización de contraseñas y actualiza la contraseña de la base de datos de SSO directamente desde Windows.  
  
 La sincronización directa de contraseña desde Windows resulta de utilidad en los siguientes casos:  
  
-   Cuando el sistema de la empresa requiere una asignación de Windows a Windows.  
  
-   Cuando se produce un cambio de contraseña en un usuario de Windows, debe actualizar directamente la contraseña de usuario externo en la base de datos de SSO. La contraseña del sistema de servidor (la correspondiente al usuario externo) puede cambiarse con otros mecanismos. Por ejemplo, puede utilizar Microsoft Identity Integration Server para actualizar las contraseñas de Resource Access Control Facility (RACF) en grandes sistemas IBM que utilizan el agente de administración RACF.  
  
### <a name="to-enable-direct-password-sync"></a>Para habilitar la sincronización directa de contraseñas  
  
1.  Abra el Inicio de sesión único empresarial.  
  
2.  En el panel de ámbito, haga clic en **aplicaciones afiliadas**.  
  
3.  Haga clic en la correspondiente **aplicación afiliada**.  
  
4.  Haga clic en **Propiedades**.  
  
     El **propiedades de aplicaciones afiliadas** aparece el cuadro de diálogo.  
  
5.  Haga clic en el **opciones** ficha.  
  
6.  Seleccione el **sincronización directa de contraseña desde Windows** casilla de verificación.  
  
7.  Haga clic en **Aceptar**.