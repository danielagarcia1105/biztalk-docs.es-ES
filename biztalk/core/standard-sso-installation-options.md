---
title: Opciones de instalación de SSO estándar | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, installing
ms.assetid: 59aeb503-f369-4145-8a3c-ab60e9ed31a8
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a734114bb6d89c73b275e1060719c6b2cb638566
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981725"
---
# <a name="standard-sso-installation-options"></a>Opciones de instalación de SSO estándar
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aprovecha las funciones de inicio de sesión único (SSO) empresarial para almacenar credenciales de forma segura y habilitar escenarios de inicio de sesión único.  
  
 Asimismo, BizTalk Server utiliza SSO para almacenar de forma segura datos de configuración personalizada de adaptadores. Para realizar esto, las características de tiempo de ejecución y de administración de BizTalk Server instalan SSO como una característica dependiente. La instalación predeterminada de BizTalk Server instala SSO empresarial.  
  
> [!NOTE]
>  Cuando se instala el inicio de sesión único empresarial (componente Servidor), se debe realizar la configuración. El primer paso para configurar un sistema de SSO es configurar el servidor secreto principal. Se recomienda configurar un servidor secreto principal independiente. Esto sólo se puede hacer seleccionando el inicio de sesión único empresarial del árbol de función personalizado en el programa de instalación de BizTalk Server.  
>   
>  También se recomienda que todos los equipos que ejecuten el inicio de sesión único empresarial dispongan de un servicio de sincronización de tiempo. De esta manera se mantiene la hora del equipo en sincronización con el resto del sistema, lo que resulta necesario para que los servicios de compra de vales de SSO funcionen correctamente.  
  
 **Lista de opciones de instalación**: ejecutar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] programa de instalación. Seleccione **instalación personalizada**y, a continuación, seleccione la opción adecuada en la lista siguiente:  
  
- **Administración de inicio de sesión único de Enterprise:** herramientas de administración y cliente para la asignación y conexión a servicios de inicio de inicio de sesión único de Enterprise.  
  
- **Enterprise Single Sign-On servidor secreto principal:** actúa como el servidor secreto principal en el sistema SSO. Éste es el primer servidor del sistema de SSO que es necesario implementar y le permite crear la base de datos de SSO.  
  
  Tras la instalación, también se podrán agregar los siguientes elementos mediante la utilidad Agregar o quitar programas:  
  
- **Servidor en tiempo de ejecución:** principales de servicios para habilitar el inicio de sesión único y/acceso al almacén de datos de configuración de forma segura.  
  
- **Administración de inicio de sesión único de Enterprise:** herramientas de administración y cliente para la asignación y conexión a servicios de inicio de inicio de sesión único de Enterprise.  
  
- **Único inicio de sesión en servicios empresariales con la sincronización de contraseñas:** servicios para habilitar la característica de sincronización de contraseña en el sistema de SSO empresarial. Estos servicios también se integran con el Servicio de notificación de cambio de contraseña de Microsoft. Después de haber instalado los servicios básicos de inicio de sesión único empresarial, puede instalar la característica Sincronización de contraseñas de SSO empresarial del paquete de BizTalk Server al iniciar \Platform\SSO\Setup.exe y seleccionar la característica Sincronización de contraseñas.  
  
- **Kit de desarrollo de software** programación e información de referencia.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo instalar el componente de administración de SSO](../core/how-to-install-the-sso-administration-component.md)  
  
-   [Cómo instalar la utilidad de cliente SSO](../core/how-to-install-the-sso-client-utility.md)