---
title: Actualizar desde una versión anterior de inicio de sesión único | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, SSO
- SSO, upgrading
ms.assetid: 78b99d99-9a10-4453-9db5-ae1bacd7de50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d12a4ee046fa7c7d835f0ddd16187e79d9d19c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979285"
---
# <a name="upgrading-from-a-previous-version-of-sso"></a>Actualizar desde una versión anterior de inicio de sesión único
Si va a instalar la característica de Enterprise Single Sign-on y ya tiene una versión anterior implementada en el equipo (por ejemplo, de Microsoft BizTalk Server 2009), debe completar los pasos siguientes.  
  
1. Cree una copia de seguridad de la base de datos de SSO en una ubicación segura  
  
2. Cree una copia de seguridad de la clave secreta principal en el servidor secreto principal  
  
3. Actualizar el servidor secreto principal mediante la ejecución [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de instalación, elegir **instalación personalizada**y, a continuación, seleccione **Enterprise Single Sign-On**.  
  
4. Después de seleccionar **habilitar Enterprise Single Sign-on en este equipo**, seleccione **unir un sistema SSO existente**.  
  
   No es necesario actualizar los demás servidores de SSO (servidores secretos no principales) de la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Sin embargo, si desea que las nuevas características de inicio de sesión único empresarial estén disponibles en esos servidores, debe actualizarlos siguiendo el procedimiento mencionado anteriormente.  
  
> [!NOTE]
>  Estas consideraciones también se aplican si va a instalar Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un equipo con una instalación existente de Server 2009 Enterprise Single Sign-On de integración de Host y desea actualizar los servidores.  
  
 Si va a instalar Host Integration Server en un equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ya esté instalado, no seleccione la característica de inicio de sesión único empresarial.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Uso de la funcionalidad de SSO iniciado por host](../core/using-host-initiated-sso-functionality.md)  
  
-   [Procesamiento de servidores para SSO](../core/processing-servers-for-sso.md)