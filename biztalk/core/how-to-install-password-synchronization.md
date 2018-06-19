---
title: Cómo instalar la sincronización de contraseña | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, Password Synchronization [SSO]
- Password Synchronization [SSO], installing
ms.assetid: 8ace0401-b759-4ea3-91a0-be2aa8b5a5a4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3a6a3f93e600a8e68581f09af8fcdbc77ed57af
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970938"
---
# <a name="how-to-install-password-synchronization"></a><span data-ttu-id="e85bd-102">Cómo instalar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="e85bd-102">How to Install Password Synchronization</span></span>
<span data-ttu-id="e85bd-103">Al igual que con las demás características de inicio de sesión único, Sincronización de contraseñas no se instala con la instalación predeterminada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], sino que se debe seleccionar de forma específica durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="e85bd-103">As with the other Single Sign-On features, Password Synchronization is not installed in the default [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation, and must be specifically selected during setup.</span></span>  
  
### <a name="to-install-password-synchronization"></a><span data-ttu-id="e85bd-104">Para instalar Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="e85bd-104">To install Password Synchronization</span></span>  
  
1.  <span data-ttu-id="e85bd-105">En el CD de BizTalk Server, vaya a la  **\<CDRoot\>\Platforms\SSO** carpeta.</span><span class="sxs-lookup"><span data-stu-id="e85bd-105">On the BizTalk Server CD, browse to the **\<CDRoot\>\Platforms\SSO** folder.</span></span>  
  
2.  <span data-ttu-id="e85bd-106">Ejecutar **setup.exe** y siga las instrucciones del asistente.</span><span class="sxs-lookup"><span data-stu-id="e85bd-106">Run **setup.exe** and follow the instructions in the wizard.</span></span>  
  
3.  <span data-ttu-id="e85bd-107">Seleccione el **Password Synchronization** de características y continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="e85bd-107">Select the **Password Synchronization** feature and proceed with the installation.</span></span>  
  
 <span data-ttu-id="e85bd-108">Además, se necesitan los adaptadores de sincronización de contraseñas para enviar y recibir cambios de contraseña en el sistema externo.</span><span class="sxs-lookup"><span data-stu-id="e85bd-108">In addition to this, Password synchronization adapters are necessary to send and receive password changes to the external system.</span></span> <span data-ttu-id="e85bd-109">Los temas de esta sección explican cómo configurar sus propios adaptadores.</span><span class="sxs-lookup"><span data-stu-id="e85bd-109">The topics in this section describe how to configure your own adapters.</span></span>  
  
 <span data-ttu-id="e85bd-110">También puede ponerse en contacto con los alias de soporte técnico para obtener información acerca de los adaptadores de sincronización de contraseñas disponibles.</span><span class="sxs-lookup"><span data-stu-id="e85bd-110">You can also contact support aliases to obtain information on available Password synchronization adapters.</span></span>  
  
 <span data-ttu-id="e85bd-111">Finalmente, para capturar los cambios de contraseña realizados en Active Directory, además de instalar la característica de sincronización de contraseñas de ENTSSO, es preciso instalar componentes en los controladores de dominio para capturar los cambios de contraseña.</span><span class="sxs-lookup"><span data-stu-id="e85bd-111">Finally, to capture password changes made in Active Directory, in addition to installing the ENTSSO Password Sync feature, components need to be installed on the domain controllers to capture password changes.</span></span>  
  
 <span data-ttu-id="e85bd-112">Tanto Windows Password Capture como Password Change Notification Service (PCNS) deben estar instalados en todos los controladores de dominio de los que se van a capturar contraseñas.</span><span class="sxs-lookup"><span data-stu-id="e85bd-112">Both the Windows Password Capture component and Password Change Notification Service (PCNS) must be installed on all domain controllers from which you will be capturing passwords.</span></span> <span data-ttu-id="e85bd-113">Puede instalar estos componentes desde la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="e85bd-113">You can install these components from the following location:</span></span>  
  
 [<span data-ttu-id="e85bd-114">http://go.Microsoft.com/fwlink/?LinkId=68145</span><span class="sxs-lookup"><span data-stu-id="e85bd-114">http://go.microsoft.com/fwlink/?LinkId=68145</span></span>](http://go.microsoft.com/fwlink/?LinkId=68145)  
  
 <span data-ttu-id="e85bd-115">Lea la documentación que los acompaña (también en esta carpeta) antes de proceder con la instalación en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="e85bd-115">Read the accompanying documentation (also located in this folder) before you proceed with the installation on the domain controller.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e85bd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e85bd-116">See Also</span></span>  
 [<span data-ttu-id="e85bd-117">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="e85bd-117">Password Synchronization</span></span>](../core/password-synchronization2.md)