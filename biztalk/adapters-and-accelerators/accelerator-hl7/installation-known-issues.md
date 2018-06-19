---
title: Problemas conocidos de instalación | Documentos de Microsoft
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
ms.openlocfilehash: bf4e9197d2b3c448b4fd9cc42c0cdeb929917061
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204548"
---
# <a name="installation-known-issues"></a><span data-ttu-id="ef79a-102">Problemas conocidos de instalación</span><span class="sxs-lookup"><span data-stu-id="ef79a-102">Installation known issues</span></span>
<span data-ttu-id="ef79a-103">Información útil que puede ayudar a evitar problemas de instalación.</span><span class="sxs-lookup"><span data-stu-id="ef79a-103">Useful information that may help you avoid installation problems.</span></span>  
  
## <a name="prerequisites-for-installing-btahl7"></a><span data-ttu-id="ef79a-104">Requisitos previos para la instalación de BTAHL7</span><span class="sxs-lookup"><span data-stu-id="ef79a-104">Prerequisites for installing BTAHL7</span></span>  
 <span data-ttu-id="ef79a-105">Los requisitos previos para la instalación de [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef79a-105">The prerequisites for installing [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] include the following:</span></span>  
  
-   <span data-ttu-id="ef79a-106">Componentes básicos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], incluido el inicio de sesión único (SSO) empresarial, grupo y en tiempo de ejecución, debe configurarse.</span><span class="sxs-lookup"><span data-stu-id="ef79a-106">Basic components of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], including Enterprise Single Sign-On (SSO), Group, and Runtime, should be configured.</span></span>  
  
-   <span data-ttu-id="ef79a-107">El usuario de instalación y configuración de BTAHL7 debe ser un miembro del grupo Administradores de BizTalk y un miembro del grupo Administradores en el servidor de SQL Server donde se almacenan los datos de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="ef79a-107">The user installing and configuring BTAHL7 must be a member of the BizTalk Administrators group, and a member of the Administrators group on the SQL Server where the BTAHL7 data is stored.</span></span>
  
## <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="ef79a-108">Modo mixto de SQL Server no admitido</span><span class="sxs-lookup"><span data-stu-id="ef79a-108">SQL Server mixed mode not supported</span></span>  
<span data-ttu-id="ef79a-109">El [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] no es compatible con SQL Server en modo mixto.</span><span class="sxs-lookup"><span data-stu-id="ef79a-109">The [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] does not support SQL Server in mixed mode.</span></span>  
  
## <a name="repair-does-not-work-from-uninstallchange"></a><span data-ttu-id="ef79a-110">La reparación no funciona desde desinstalar o cambiar</span><span class="sxs-lookup"><span data-stu-id="ef79a-110">Repair does not work from uninstall/change</span></span>  
<span data-ttu-id="ef79a-111">Si está habilitado el control de acceso de usuario (UAC), e intenta reparar la instalación mediante el panel de control, se produce un error en la reparación.</span><span class="sxs-lookup"><span data-stu-id="ef79a-111">If user access control (UAC) is enabled, and you try to repair your installation using the control panel, the repair fails.</span></span> 

<span data-ttu-id="ef79a-112">Microsoft recomienda que mantener habilitado UAC.</span><span class="sxs-lookup"><span data-stu-id="ef79a-112">Microsoft recommends you keep UAC enabled.</span></span>

 <span data-ttu-id="ef79a-113">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="ef79a-113">**Resolution**</span></span>  
  
 <span data-ttu-id="ef79a-114">Ejecute el [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.exe y, a continuación, seleccione **reparación**.</span><span class="sxs-lookup"><span data-stu-id="ef79a-114">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.exe, and then select **Repair**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef79a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef79a-115">See Also</span></span>  
[<span data-ttu-id="ef79a-116">Instalar o actualizar Acelerador de Microsoft BizTalk para HL7</span><span class="sxs-lookup"><span data-stu-id="ef79a-116">Install or upgrade Microsoft BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)