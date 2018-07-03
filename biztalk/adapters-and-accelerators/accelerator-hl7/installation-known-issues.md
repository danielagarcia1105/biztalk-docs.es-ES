---
title: Problemas conocidos de instalación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2f80ff9-b37c-49f8-8250-fcf3cec4c0fc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f017fa273d91d1c40727ba34c6d047383054d52
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000925"
---
# <a name="installation-known-issues"></a><span data-ttu-id="41d8c-102">Problemas de instalación conocidos</span><span class="sxs-lookup"><span data-stu-id="41d8c-102">Installation known issues</span></span>
<span data-ttu-id="41d8c-103">Información útil que puede ayudar a evitar problemas de instalación.</span><span class="sxs-lookup"><span data-stu-id="41d8c-103">Useful information that may help you avoid installation problems.</span></span>  
  
## <a name="prerequisites-for-installing-btahl7"></a><span data-ttu-id="41d8c-104">Requisitos previos para la instalación de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="41d8c-104">Prerequisites for installing BTAHL7</span></span>  
 <span data-ttu-id="41d8c-105">Los requisitos previos para instalar [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41d8c-105">The prerequisites for installing [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] include the following:</span></span>  
  
- <span data-ttu-id="41d8c-106">Componentes básicos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], incluidos el inicio de sesión único (SSO) empresarial, grupo y en tiempo de ejecución, debe estar configurado.</span><span class="sxs-lookup"><span data-stu-id="41d8c-106">Basic components of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], including Enterprise Single Sign-On (SSO), Group, and Runtime, should be configured.</span></span>  
  
- <span data-ttu-id="41d8c-107">El usuario de instalación y configuración de BTAHL7 debe ser miembro del grupo Administradores de BizTalk y un miembro del grupo Administradores en el servidor SQL donde se almacenan los datos de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="41d8c-107">The user installing and configuring BTAHL7 must be a member of the BizTalk Administrators group, and a member of the Administrators group on the SQL Server where the BTAHL7 data is stored.</span></span>
  
## <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="41d8c-108">Modo mixto de SQL Server no admitido</span><span class="sxs-lookup"><span data-stu-id="41d8c-108">SQL Server mixed mode not supported</span></span>  
<span data-ttu-id="41d8c-109">El [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] no es compatible con SQL Server en modo mixto.</span><span class="sxs-lookup"><span data-stu-id="41d8c-109">The [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] does not support SQL Server in mixed mode.</span></span>  
  
## <a name="repair-does-not-work-from-uninstallchange"></a><span data-ttu-id="41d8c-110">La reparación no funciona desde desinstalar o cambiar</span><span class="sxs-lookup"><span data-stu-id="41d8c-110">Repair does not work from uninstall/change</span></span>  
<span data-ttu-id="41d8c-111">Si está habilitado el control de acceso de usuario (UAC), e intenta reparar la instalación mediante el panel de control, se produce un error en la reparación.</span><span class="sxs-lookup"><span data-stu-id="41d8c-111">If user access control (UAC) is enabled, and you try to repair your installation using the control panel, the repair fails.</span></span> 

<span data-ttu-id="41d8c-112">Microsoft recomienda que mantienen habilitado UAC.</span><span class="sxs-lookup"><span data-stu-id="41d8c-112">Microsoft recommends you keep UAC enabled.</span></span>

 <span data-ttu-id="41d8c-113">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="41d8c-113">**Resolution**</span></span>  
  
 <span data-ttu-id="41d8c-114">Ejecute el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.exe y, a continuación, seleccione **reparación**.</span><span class="sxs-lookup"><span data-stu-id="41d8c-114">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.exe, and then select **Repair**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d8c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="41d8c-115">See Also</span></span>  
[<span data-ttu-id="41d8c-116">Instalar o actualizar el Acelerador de Microsoft BizTalk para HL7</span><span class="sxs-lookup"><span data-stu-id="41d8c-116">Install or upgrade Microsoft BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)