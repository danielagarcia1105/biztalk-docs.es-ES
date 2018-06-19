---
title: Exportar aplicaciones de BizTalk, los enlaces y directivas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, exporting
- exporting, policies
- bindings, exporting
- exporting, applications
- applications, exporting
- exporting, bindings
ms.assetid: ac101206-be49-47c9-a354-4f39e8b77acf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d6df445b0fefc132940a736870d66c62329ce60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245812"
---
# <a name="exporting-biztalk-applications-bindings-and-policies"></a><span data-ttu-id="ed59f-102">Exportar aplicaciones, enlaces y directivas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ed59f-102">Exporting BizTalk Applications, Bindings, and Policies</span></span>
<span data-ttu-id="ed59f-103">En esta sección se describe cómo exportar una aplicación, enlaces o directivas de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ed59f-103">This section describes how to export a BizTalk application, bindings, or policies.</span></span> <span data-ttu-id="ed59f-104">Puede exportar algunos o todos los artefactos que contiene una aplicación de BizTalk, o bien puede exportar únicamente sus enlaces o directivas.</span><span class="sxs-lookup"><span data-stu-id="ed59f-104">You can export some or all of the artifacts contained in a BizTalk application, or you can export only its bindings or policies.</span></span> <span data-ttu-id="ed59f-105">Al exportar una aplicación se crea un archivo (.msi) de Windows Installer que contiene los artefactos de la aplicación seleccionados para que se exportaran.</span><span class="sxs-lookup"><span data-stu-id="ed59f-105">Exporting an application creates a Windows Installer (.msi) file containing the application artifacts that you selected for export.</span></span> <span data-ttu-id="ed59f-106">Al exportar enlaces o directivas se crea un archivo .xml de esos enlaces o directivas.</span><span class="sxs-lookup"><span data-stu-id="ed59f-106">Exporting bindings or policies creates an .xml file of the bindings or policies.</span></span> <span data-ttu-id="ed59f-107">Para obtener información general acerca de este proceso, consulte [¿qué ocurre cuando los artefactos se exportan](../core/what-happens-when-artifacts-are-exported.md).</span><span class="sxs-lookup"><span data-stu-id="ed59f-107">For background information on this process, see [What Happens When Artifacts Are Exported](../core/what-happens-when-artifacts-are-exported.md).</span></span>  
  
 <span data-ttu-id="ed59f-108">Puede importar un archivo .msi de aplicación en otro grupo de BizTalk para crear una nueva aplicación que contenga los artefactos de la aplicación de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="ed59f-108">You can import an application .msi file into another BizTalk group to create a new application that contains the application's artifacts in that group.</span></span> <span data-ttu-id="ed59f-109">Puede importar un archivo .xml de enlaces o directivas en otra aplicación de BizTalk para utilizar esos enlaces o directivas.</span><span class="sxs-lookup"><span data-stu-id="ed59f-109">You can import a binding or policy .xml file into another BizTalk application to use the bindings or policies.</span></span> <span data-ttu-id="ed59f-110">Se describe cómo importar artefactos en [importar aplicaciones de BizTalk, los enlaces y directivas](../core/importing-biztalk-applications-bindings-and-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ed59f-110">How to import artifacts is described in [Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ed59f-111">Almacene los archivos de enlaces en una ubicación segura, ya que pueden contener datos económicos importantes, como información de conectividad y de configuración.</span><span class="sxs-lookup"><span data-stu-id="ed59f-111">Store binding files in a secure location, as they may contain critical business data such as connectivity and configuration information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed59f-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ed59f-112">In This Section</span></span>  
  
-   [<span data-ttu-id="ed59f-113">Cómo exportar una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="ed59f-113">How to Export a BizTalk Application</span></span>](../core/how-to-export-a-biztalk-application.md)  
  
-   [<span data-ttu-id="ed59f-114">Exportar enlaces</span><span class="sxs-lookup"><span data-stu-id="ed59f-114">Exporting Bindings</span></span>](../core/exporting-bindings6.md)  
  
-   [<span data-ttu-id="ed59f-115">Cómo exportar una directiva</span><span class="sxs-lookup"><span data-stu-id="ed59f-115">How to Export a Policy</span></span>](../core/how-to-export-a-policy.md)