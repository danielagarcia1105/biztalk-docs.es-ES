---
title: Cómo usar el agente de administración de ENTSSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c89b494-db12-4d2a-a030-6acd34489cab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c0f7d2c04a2707cf965f64ff7a559d8642a12c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256140"
---
# <a name="how-to-use-the-entsso-management-agent"></a><span data-ttu-id="e771e-102">Uso del agente de administración ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e771e-102">How to Use the ENTSSO Management Agent</span></span>
<span data-ttu-id="e771e-103">Esta versión de Enterprise Single Sign-On (SSO) contiene un agente de administración para Microsoft Identity Integration Server (MIIS), que integra SSO empresarial con las capacidades de sincronización de cuentas de MIIS.</span><span class="sxs-lookup"><span data-stu-id="e771e-103">This version of Enterprise Single Sign-On (SSO) contains a Management Agent (MA) for Microsoft Identity Integration Server (MIIS), which integrates Enterprise SSO with the account synchronization capabilities of MIIS.</span></span> <span data-ttu-id="e771e-104">Esto habilita al administrador de MIIS para administrar asignaciones de SSO en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="e771e-104">This enables an MIIS administrator to manage SSO mappings in the SSO Database.</span></span>  
  
 <span data-ttu-id="e771e-105">En SSO empresarial, se crean asignaciones entre cuentas de dominio de Windows (*ombreDeUsuario*) y credenciales externas.</span><span class="sxs-lookup"><span data-stu-id="e771e-105">In Enterprise SSO, mappings are created between Windows Domain accounts (*domainname\username*) and external credentials.</span></span> <span data-ttu-id="e771e-106">Si tiene un agente de administración de Active Directory y el agente de administración para el origen de datos externo (ejemplo: RACF MA), puede usar el SSO empresarial (ENTSSO MA) del agente de administración para administrar las asignaciones en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="e771e-106">If you have an Active Directory Management Agent, and the Management Agent for the external Data Source (example: RACF MA), you can use the Enterprise SSO MA (ENTSSO MA) to manage mappings in the SSO Database.</span></span> <span data-ttu-id="e771e-107">ENTSSO MA es un *exportación basada en llamadas* solo agente de administración.</span><span class="sxs-lookup"><span data-stu-id="e771e-107">ENTSSO MA is a *Call-Based Export* Management Agent only.</span></span>  
  
 <span data-ttu-id="e771e-108">Configure el agente de administración en tres partes independientes:</span><span class="sxs-lookup"><span data-stu-id="e771e-108">You configure the Management Agent in three separate parts:</span></span>  
  
-   <span data-ttu-id="e771e-109">Un archivo de configuración (ENTSSO.xml)</span><span class="sxs-lookup"><span data-stu-id="e771e-109">A configuration file (ENTSSO.xml)</span></span>  
  
-   <span data-ttu-id="e771e-110">La interfaz de usuario de MIIS</span><span class="sxs-lookup"><span data-stu-id="e771e-110">The MIIS user interface</span></span>  
  
-   <span data-ttu-id="e771e-111">La interfaz de usuario de ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e771e-111">The ENTSSO user interface</span></span>  
  
 <span data-ttu-id="e771e-112">Los temas de esta sección describen el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="e771e-112">The topics in this section describe the configuration process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e771e-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e771e-113">In This Section</span></span>  
  
-   [<span data-ttu-id="e771e-114">Configurar el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="e771e-114">Configuring the XML File</span></span>](../core/configuring-the-xml-file.md)  
  
-   [<span data-ttu-id="e771e-115">Cómo configurar MIIS para ENTSSO MA</span><span class="sxs-lookup"><span data-stu-id="e771e-115">How to Configure MIIS for ENTSSO MA</span></span>](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [<span data-ttu-id="e771e-116">Cómo configurar ENTSSO para la sincronización de contraseña MIIS</span><span class="sxs-lookup"><span data-stu-id="e771e-116">How to Configure ENTSSO for MIIS Password Sync</span></span>](../core/how-to-configure-entsso-for-miis-password-sync.md)