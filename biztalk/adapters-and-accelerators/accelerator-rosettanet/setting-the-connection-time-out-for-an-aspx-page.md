---
title: "Establecer el tiempo de espera de conexión para una página ASPX | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ASPX pages, connection time-out
- connections, time-out
ms.assetid: 61d9c996-caf4-48bd-bda7-52f2797a941b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83e083b9f2f0262095e58b4ed9842627888773dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-connection-time-out-for-an-aspx-page"></a>Establecer el tiempo de espera de conexión para una página ASPX
Cuando se usa una página ASPX para mensajes sincrónicos, debe aumentar el tiempo de espera de conexión de la página ASPX, por lo que puede esperar a que el mensaje esperado.  
  
 Aumentar el tiempo de espera de conexión de la página ASPX puede tener consecuencias no deseadas. En primer lugar, aumenta el riesgo de un ataque de denegación de servicio y la amenaza de agotar el grupo de subprocesos. En segundo lugar, si hay demasiadas conexiones sincrónicas en la página ASPX, puede bloquear el sistema de. Por lo tanto, mientras que debe aumentar el tiempo de espera de conexión, tenga cuidado de no lo aumente demasiado.  
  
 Establece el tiempo de espera de conexión en el mínimo permitido por la organización RosettaNet. Para obtener más información acerca de los parámetros de control de tiempo para un proceso de interfaz de socio (PIP), consulte la tabla 4-3: controles de intercambio de mensajes, en la especificación de PIP de RosettaNet.  
  
### <a name="to-set-the-connection-time-out-for-the-aspx-page"></a>Para establecer el tiempo de espera de conexión de la página ASPX  
  
1.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.  
  
2.  En el Administrador de IIS, expanda el nodo para el equipo local y, a continuación, expanda **sitios Web**.  
  
3.  Haga clic con el botón secundario en **Sitio web predeterminado**y, después, en **Propiedades**.  
  
4.  En el cuadro de diálogo Propiedades del sitio Web predeterminado, en la **sitio Web** ficha la **tiempo de espera de conexión** , escriba un valor adecuado y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)