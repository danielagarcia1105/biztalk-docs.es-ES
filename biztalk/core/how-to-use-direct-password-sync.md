---
title: "Cómo usar la sincronización de contraseña directa | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1334c2f-2020-46ea-a98c-f7688813e38c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6080589271d845432e875cb335a2ef354c9784ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-direct-password-sync"></a><span data-ttu-id="f0f74-102">Cómo utilizar la sincronización directa de contraseñas</span><span class="sxs-lookup"><span data-stu-id="f0f74-102">How to Use Direct Password Sync</span></span>
<span data-ttu-id="f0f74-103">Esta versión del inicio de sesión único empresarial incluye la característica de sincronización directa de contraseña desde Windows.</span><span class="sxs-lookup"><span data-stu-id="f0f74-103">This version of Enterprise Single Sign-On includes the Direct Password Sync from Windows feature.</span></span> <span data-ttu-id="f0f74-104">Esta característica le permite evitar el uso del adaptador de sincronización de contraseñas y actualiza la contraseña de la base de datos de SSO directamente desde Windows.</span><span class="sxs-lookup"><span data-stu-id="f0f74-104">This enables you to bypass a Password Sync Adapter and update the password in the SSO Database directly from Windows.</span></span>  
  
 <span data-ttu-id="f0f74-105">La sincronización directa de contraseña desde Windows resulta de utilidad en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="f0f74-105">Direct Password Sync from Windows is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="f0f74-106">Cuando el sistema de la empresa requiere una asignación de Windows a Windows.</span><span class="sxs-lookup"><span data-stu-id="f0f74-106">Your enterprise system requires Windows to Windows mapping.</span></span>  
  
-   <span data-ttu-id="f0f74-107">Cuando se produce un cambio de contraseña en un usuario de Windows, debe actualizar directamente la contraseña de usuario externo en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="f0f74-107">You need to update the External User’s password in the SSO database directly when a password change occurs for the Windows user.</span></span> <span data-ttu-id="f0f74-108">La contraseña del sistema de servidor (la correspondiente al usuario externo) puede cambiarse con otros mecanismos.</span><span class="sxs-lookup"><span data-stu-id="f0f74-108">You can change the password on the back-end system (that corresponds to the external user) by using other mechanisms.</span></span> <span data-ttu-id="f0f74-109">Por ejemplo, puede utilizar Microsoft Identity Integration Server para actualizar las contraseñas de Resource Access Control Facility (RACF) en grandes sistemas IBM que utilizan el agente de administración RACF.</span><span class="sxs-lookup"><span data-stu-id="f0f74-109">For example, you can use Microsoft Identity Integration Server to update passwords in Resource Access Control Facility (RACF) on an IBM Mainframe using the RACF Management Agent.</span></span>  
  
### <a name="to-enable-direct-password-sync"></a><span data-ttu-id="f0f74-110">Para habilitar la sincronización directa de contraseñas</span><span class="sxs-lookup"><span data-stu-id="f0f74-110">To enable Direct Password Sync</span></span>  
  
1.  <span data-ttu-id="f0f74-111">Abra el Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="f0f74-111">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="f0f74-112">En el panel de ámbito, haga clic en **aplicaciones afiliadas**.</span><span class="sxs-lookup"><span data-stu-id="f0f74-112">In the scope pane, click **Affiliate Applications**.</span></span>  
  
3.  <span data-ttu-id="f0f74-113">Haga clic en la correspondiente **aplicación afiliada**.</span><span class="sxs-lookup"><span data-stu-id="f0f74-113">Right-click the appropriate **Affiliate Application**.</span></span>  
  
4.  <span data-ttu-id="f0f74-114">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f0f74-114">Click **Properties**.</span></span>  
  
     <span data-ttu-id="f0f74-115">El **propiedades de aplicaciones afiliadas** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f0f74-115">The **Affiliate Applications Properties** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="f0f74-116">Haga clic en el **opciones** ficha.</span><span class="sxs-lookup"><span data-stu-id="f0f74-116">Click the **Options** tab.</span></span>  
  
6.  <span data-ttu-id="f0f74-117">Seleccione el **sincronización directa de contraseña desde Windows** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="f0f74-117">Select the **Direct Password Sync from Windows** check box.</span></span>  
  
7.  <span data-ttu-id="f0f74-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0f74-118">Click **OK**.</span></span>