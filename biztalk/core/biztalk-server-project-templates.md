---
title: Plantillas de proyecto de Visual Studio | Microsoft Docs
description: Describe el .btproj, BPEL y plantillas de Visual Studio .btaproj usadas por BizTalk Server
ms.custom: ''
ms.date: 11/07/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2b3d494-db80-4314-afcd-d08d5a26e211
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14d35eb4f12bdb7a66da28d94c8fabd33b073127
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018376"
---
# <a name="biztalk-server-project-templates"></a><span data-ttu-id="7d801-103">Plantillas de proyecto de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7d801-103">BizTalk Server Project Templates</span></span>

## <a name="overview"></a><span data-ttu-id="7d801-104">Información general</span><span class="sxs-lookup"><span data-stu-id="7d801-104">Overview</span></span>
<span data-ttu-id="7d801-105">Al instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la instalación agrega la carpeta de proyectos de BizTalk para el **nuevo proyecto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7d801-105">When you install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the installation adds the BizTalk Projects folder to the **New Project** dialog box.</span></span> <span data-ttu-id="7d801-106">La carpeta de proyectos de BizTalk contiene plantillas para crear un proyecto vacío de servidor BizTalk Server, el proyecto de importación BPEL de BizTalk Server y un proyecto de aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7d801-106">The BizTalk Projects folder contains templates for creating an empty BizTalk Server project, BizTalk Server BPEL Import project, and a BizTalk Server Application Project.</span></span>

## <a name="available-templates"></a><span data-ttu-id="7d801-107">Plantillas disponibles</span><span class="sxs-lookup"><span data-stu-id="7d801-107">Available templates</span></span>
<span data-ttu-id="7d801-108">En la tabla siguiente se describe estas plantillas de proyecto.</span><span class="sxs-lookup"><span data-stu-id="7d801-108">The following table describes these project templates.</span></span>  


|                     <span data-ttu-id="7d801-109">Use</span><span class="sxs-lookup"><span data-stu-id="7d801-109">Use this</span></span>                      |                                                                                                                                                                   <span data-ttu-id="7d801-110">Para</span><span class="sxs-lookup"><span data-stu-id="7d801-110">To do this</span></span>                                                                                                                                                                   |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         <span data-ttu-id="7d801-111">**Proyecto vacío de servidor BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="7d801-111">**Empty BizTalk Server Project**</span></span>          |                                                                                                                                                  <span data-ttu-id="7d801-112">Crea un nuevo proyecto vacío de servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7d801-112">Creates a new empty BizTalk Server project.</span></span>                                                                                                                                                   |
|      <span data-ttu-id="7d801-113">**Proyecto de importación BPEL de servidor BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="7d801-113">**BizTalk Server BPEL Import Project**</span></span>       |                                                                                      <span data-ttu-id="7d801-114">Importa archivos de lenguaje de ejecución de procesos empresariales (BPEL), lenguaje de descripción de servicios Web (WSDL) o lenguaje de definición de esquemas XML (XSD) a un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7d801-114">Imports Business Process Execution Language (BPEL), Web Services Description Language (WSDL), or XML Schema Definition Language (XSD) files into a BizTalk project.</span></span>                                                                                       |
| <span data-ttu-id="7d801-115">**Proyecto de aplicación de BizTalk Server (.btaproj)**</span><span class="sxs-lookup"><span data-stu-id="7d801-115">**BizTalk Server Application Project (.btaproj)**</span></span> | <span data-ttu-id="7d801-116">A partir de [!INCLUDE[bts2016](../includes/bts2016-md.md)] [Feature Pack 1](../core/configure-the-feature-pack.md), o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="7d801-116">Starting with [!INCLUDE[bts2016](../includes/bts2016-md.md)] [Feature Pack 1](../core/configure-the-feature-pack.md), or later.</span></span> <br/><br/><span data-ttu-id="7d801-117">Se usa para implementar y actualizar automáticamente aplicaciones con Visual Studio Team Services (VSTS).</span><span class="sxs-lookup"><span data-stu-id="7d801-117">Used to automatically deploy and update applications using Visual Studio Team Services (VSTS).</span></span> <span data-ttu-id="7d801-118">El proyecto contiene un `BizTalkServerInventory.json` archivo que se utiliza VSTS durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="7d801-118">The project contains a `BizTalkServerInventory.json` file that is used by VSTS during the deployment.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7d801-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d801-119">See Also</span></span>  
 [<span data-ttu-id="7d801-120">Trabajar con proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7d801-120">Working with BizTalk Projects</span></span>](../core/working-with-biztalk-projects.md)
