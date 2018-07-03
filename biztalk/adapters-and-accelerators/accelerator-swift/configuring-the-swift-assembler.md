---
title: Configuración del ensamblador de SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, assembler
ms.assetid: 76944226-e29b-4a7f-a4ab-3c3d5f13ec51
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50c58ad000e465949229400128ce4c47da40806e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993669"
---
# <a name="configuring-the-swift-assembler"></a><span data-ttu-id="c2aa9-102">Configuración del ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="c2aa9-102">Configuring the SWIFT Assembler</span></span>
<span data-ttu-id="c2aa9-103">El ensamblador de SWIFT realiza las tareas siguientes cuando se invoca en una Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalización de envío:</span><span class="sxs-lookup"><span data-stu-id="c2aa9-103">The SWIFT assembler performs the following tasks when you invoke it in a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] send pipeline:</span></span>  
  
- <span data-ttu-id="c2aa9-104">Detecta el tipo de mensaje dinámicamente y se resuelve el esquema de documento</span><span class="sxs-lookup"><span data-stu-id="c2aa9-104">Dynamically discovers the message type and resolves the document schema</span></span>  
  
- <span data-ttu-id="c2aa9-105">Serializa el XML analizado en archivos planos SWIFT</span><span class="sxs-lookup"><span data-stu-id="c2aa9-105">Serializes parsed XML into SWIFT flat files</span></span>  
  
  <span data-ttu-id="c2aa9-106">Puede configurar la codificación juego de caracteres utilizado para codificar el resultado serializado (por ejemplo, para utilizar la codificación ASCII o Unicode).</span><span class="sxs-lookup"><span data-stu-id="c2aa9-106">You can configure the encoding character set used for encoding the serialized output (for example, to use ASCII or Unicode encoding).</span></span>  
  
  <span data-ttu-id="c2aa9-107">Configure el ensamblador de SWIFT durante el desarrollo de la canalización de envío personalizada que utiliza el ensamblador de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="c2aa9-107">You configure the SWIFT assembler during development time of the custom send pipeline that uses the SWIFT assembler.</span></span>  
  
  <span data-ttu-id="c2aa9-108">Diseñador de canalizaciones de BizTalk se configura el ensamblador de SWIFT durante el desarrollo de la canalización de envío personalizada.</span><span class="sxs-lookup"><span data-stu-id="c2aa9-108">BizTalk Pipeline Designer configures the SWIFT assembler during development time of the custom send pipeline.</span></span>  
  
  <span data-ttu-id="c2aa9-109">Para configurar el Desensamblador de SWIFT después de que se ha agregado a la fase de ensamblado de canalización de envío personalizada, seleccione el componente de ensamblador de SWIFT en el lienzo del Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="c2aa9-109">To configure the SWIFT assembler after it has been added to the assemble stage of a custom send pipeline, select the SWIFT assembler component on the Pipeline Designer canvas.</span></span> <span data-ttu-id="c2aa9-110">El ensamblador de SWIFT, a continuación, recibe el foco, y puede establecer sus propiedades de configuración mediante la ventana Propiedades de Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2aa9-110">The SWIFT assembler then receives focus, and you can set its configuration properties using the Properties window within Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span>  
  
  <span data-ttu-id="c2aa9-111">Para una tabla de propiedades de configuración disponibles y sus descripciones y los detalles de uso, consulte [propiedades de configuración del ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c2aa9-111">For a table of available configuration properties and their descriptions and usage details, see [SWIFT Assembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md).</span></span>  
  
  <span data-ttu-id="c2aa9-112">Para obtener información sobre cómo usar el ensamblador de SWIFT para diferentes escenarios y establecer las propiedades de configuración, consulte [trabajar con el Desensamblador de SWIFT y ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span><span class="sxs-lookup"><span data-stu-id="c2aa9-112">For information about using the SWIFT assembler for different scenarios and setting the configuration properties, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
  <span data-ttu-id="c2aa9-113">Cuando se compila el archivo binario de canalización personalizado, estáticamente escribe los valores de configuración a la canalización personalizada.</span><span class="sxs-lookup"><span data-stu-id="c2aa9-113">When the custom pipeline binary is compiled, it statically writes the configuration settings to the custom pipeline.</span></span> <span data-ttu-id="c2aa9-114">Por lo tanto, no se puede cambiar las propiedades de configuración durante la implementación o tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c2aa9-114">Therefore, you cannot change configuration properties during deployment or run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2aa9-115">Después configura, compila e implementa una canalización personalizada, los cambios en la configuración requieren volver a compilar y volver a implementar la canalización personalizada.</span><span class="sxs-lookup"><span data-stu-id="c2aa9-115">After you configure, compile, and deploy a custom pipeline, changes in the configuration require recompiling and redeployment of the custom pipeline.</span></span>  
  
 <span data-ttu-id="c2aa9-116">Para obtener información acerca de cómo crear, compilar e implementar canalizaciones personalizadas, consulte la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c2aa9-116">For information about creating, building, and deploying custom pipelines, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="c2aa9-117">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="c2aa9-117">This section contains:</span></span>  
  
-   [<span data-ttu-id="c2aa9-118">Propiedades de configuración del ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="c2aa9-118">SWIFT Assembler Configuration Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)