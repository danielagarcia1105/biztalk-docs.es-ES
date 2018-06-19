---
title: Cómo agregar un artefacto de 64 bits a una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, 64-bit support
- scripts, 64-bit support
- virtual directories, 64-bit support
- artifacts, applications
- 64-bit support, COM components
- 64-bit support, virtual directories
- applications, artifacts
- 64-bit support, scripts
- 64-bit support, artifacts
- COM components, 64-bit support
- BizTalk Server, 64-bit support
- applications, 64-bit support
ms.assetid: 46aca7d4-c5be-421e-b16d-7f3095c8cc67
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69707401fee8b7f48b30a79bab166a9f22c29a89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246628"
---
# <a name="how-to-add-a-64-bit-artifact-to-an-application"></a><span data-ttu-id="47a2d-102">Cómo agregar un artefacto de 64 bits a una aplicación</span><span class="sxs-lookup"><span data-stu-id="47a2d-102">How to Add a 64-Bit Artifact to an Application</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="47a2d-103">incluye compatibilidad con aplicaciones de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="47a2d-103"> includes support for 64-bit applications.</span></span> <span data-ttu-id="47a2d-104">Esto significa que puede agregar artefactos de 64 bits a una aplicación de BizTalk de la misma manera que los artefactos de 32 bits; no obstante, se pueden producir los siguientes problemas al instalar los siguientes artefactos de 64 bits en un equipo de 32 bits:</span><span class="sxs-lookup"><span data-stu-id="47a2d-104">This means that you can add 64-bit artifacts to a BizTalk application in the same manner as 32-bit artifacts; however, you may encounter the following issues when installing the following 64-bit artifacts on a 32-bit computer:</span></span>  
  
-   <span data-ttu-id="47a2d-105">**Directorio virtual desde un servidor Web que se ejecuta un proceso de trabajo de 64 bits.**</span><span class="sxs-lookup"><span data-stu-id="47a2d-105">**Virtual directory from a Web server that is running a 64-bit worker process.**</span></span> <span data-ttu-id="47a2d-106">el directorio virtual se instalará en un equipo de 32 bits pero es posible que no funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="47a2d-106">The virtual directory will install on a 32-bit computer, but it may not function correctly.</span></span> <span data-ttu-id="47a2d-107">Se registrará una falta de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="47a2d-107">A mismatch will be logged.</span></span>  
  
-   <span data-ttu-id="47a2d-108">**Componentes no administrados COM o COM + administrados marcan como 64 bits.**</span><span class="sxs-lookup"><span data-stu-id="47a2d-108">**Unmanaged COM or Managed COM+ components marked as 64 bit.**</span></span> <span data-ttu-id="47a2d-109">estos componentes no se instalarán en un equipo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="47a2d-109">These components will not install on a 32-bit computer.</span></span>  
  
-   <span data-ttu-id="47a2d-110">**secuencias de comandos de 64 bits guardados como archivos .exe.**</span><span class="sxs-lookup"><span data-stu-id="47a2d-110">**64-bit scripts saved as .exe files.**</span></span> <span data-ttu-id="47a2d-111">es posible que este tipo de secuencias de comandos no funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="47a2d-111">This type of script may not function correctly.</span></span>  
  
 <span data-ttu-id="47a2d-112">Para obtener instrucciones generales sobre cómo agregar artefactos, vea [cómo crear o agregar un artefacto](../core/how-to-create-or-add-an-artifact.md).</span><span class="sxs-lookup"><span data-stu-id="47a2d-112">For general instructions on adding artifacts, see [How to Create or Add an Artifact](../core/how-to-create-or-add-an-artifact.md).</span></span> <span data-ttu-id="47a2d-113">Para obtener instrucciones sobre cómo agregar tipos de artefactos específicos, consulte [administrar artefactos](../core/managing-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="47a2d-113">For instructions on adding specific artifact types, see [Managing Artifacts](../core/managing-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a2d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="47a2d-114">See Also</span></span>  
 <span data-ttu-id="47a2d-115">[Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="47a2d-115">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="47a2d-116">Cómo instalar una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="47a2d-116">How to Install a BizTalk Application</span></span>](../core/how-to-install-a-biztalk-application.md)