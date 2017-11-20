---
title: Configurar el Desensamblador SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, disassembler
- disassembler, configuring
ms.assetid: f3773781-7412-421c-943c-18cc665da8d9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aa71ce6ba1d2a910626446ed45439b8c7132e75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-swift-disassembler"></a><span data-ttu-id="b02d1-102">Configurar el Desensamblador SWIFT</span><span class="sxs-lookup"><span data-stu-id="b02d1-102">Configuring the SWIFT Disassembler</span></span>
<span data-ttu-id="b02d1-103">El Desensamblador SWIFT (DASM) realiza las tareas siguientes cuando se invoca en un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalización de recepción:</span><span class="sxs-lookup"><span data-stu-id="b02d1-103">The SWIFT disassembler (DASM) performs the following tasks when you invoke it in a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
-   <span data-ttu-id="b02d1-104">Detecta el tipo de mensaje dinámicamente y resuelve el esquema del documento</span><span class="sxs-lookup"><span data-stu-id="b02d1-104">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="b02d1-105">Analiza los archivos planos SWIFT en XML</span><span class="sxs-lookup"><span data-stu-id="b02d1-105">Parses SWIFT flat files into XML</span></span>  
  
-   <span data-ttu-id="b02d1-106">Invoca el lector para realizar la validación XML (esquema) de validación de XML</span><span class="sxs-lookup"><span data-stu-id="b02d1-106">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
-   <span data-ttu-id="b02d1-107">Invoca el motor de reglas de negocios (BRE) para realizar la validación del BRE</span><span class="sxs-lookup"><span data-stu-id="b02d1-107">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
-   <span data-ttu-id="b02d1-108">Publica un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y la colección de errores serializado de XML</span><span class="sxs-lookup"><span data-stu-id="b02d1-108">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
-   <span data-ttu-id="b02d1-109">Lotes de entrada de procesos</span><span class="sxs-lookup"><span data-stu-id="b02d1-109">Processes inbound batches</span></span>  
  
 <span data-ttu-id="b02d1-110">Puede configurar la funcionalidad mencionada anteriormente para satisfacer los requisitos específicos para un escenario de usuario y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="b02d1-110">You can configure the functionality listed above to meet the specific requirements for a user scenario and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] solution.</span></span>  
  
 <span data-ttu-id="b02d1-111">Diseñador de canalizaciones de BizTalk se configura el Desensamblador SWIFT durante el tiempo de desarrollo de la canalización de recepción personalizada.</span><span class="sxs-lookup"><span data-stu-id="b02d1-111">BizTalk Pipeline Designer configures the SWIFT disassembler during development time of the custom receive pipeline.</span></span>  
  
 <span data-ttu-id="b02d1-112">Para configurar el Desensamblador SWIFT una vez agregada a la fase de desensamblado de una canalización de recepción personalizada, seleccione el componente de desensamblador SWIFT en el lienzo del Diseñador de canalizaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b02d1-112">To configure the SWIFT disassembler after it has been added to the disassemble stage of a custom receive pipeline, select the SWIFT disassembler component on the BizTalk Pipeline Designer canvas.</span></span> <span data-ttu-id="b02d1-113">El Desensamblador SWIFT, a continuación, recibe el foco y se puede establecer sus propiedades de configuración mediante la ventana Propiedades en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b02d1-113">The SWIFT disassembler then receives focus and you can set its configuration properties using the Properties window within [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span>  
  
 <span data-ttu-id="b02d1-114">Para una tabla de propiedades de configuración disponibles y sus descripciones y obtener detalles de uso, vea [propiedades de configuración de SWIFT Desensamblador](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b02d1-114">For a table of available configuration properties and their descriptions and usage details, see [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md).</span></span>  
  
 <span data-ttu-id="b02d1-115">Para obtener información sobre cómo usar el Desensamblador SWIFT para diferentes escenarios y establecer las propiedades de configuración, consulte [trabajar con el Desensamblador de SWIFT y de ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span><span class="sxs-lookup"><span data-stu-id="b02d1-115">For information about using the SWIFT disassembler for different scenarios and setting the configuration properties, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
 <span data-ttu-id="b02d1-116">Cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] compila la canalización personalizada binaria, estáticamente escribe los valores de configuración en la canalización personalizada.</span><span class="sxs-lookup"><span data-stu-id="b02d1-116">When [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] compiles the custom pipeline binary, it statically writes the configuration settings to the custom pipeline.</span></span> <span data-ttu-id="b02d1-117">Por lo tanto, no se puede cambiar las propiedades de configuración durante la implementación o tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b02d1-117">Therefore, you cannot change configuration properties during deployment or run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b02d1-118">Una vez que configura, compila e implementa una canalización personalizada, cambios en la configuración requieren volver a compilar y volver a implementar la canalización personalizada.</span><span class="sxs-lookup"><span data-stu-id="b02d1-118">After you configure, compile, and deploy a custom pipeline, changes in the configuration require recompiling and redeployment of the custom pipeline.</span></span>  
  
 <span data-ttu-id="b02d1-119">Para obtener información acerca de cómo crear, compilar e implementar canalizaciones personalizadas, consulte [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="b02d1-119">For information about creating, building, and deploying custom pipelines, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="b02d1-120">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="b02d1-120">This section contains:</span></span>  
  
-   [<span data-ttu-id="b02d1-121">Propiedades de configuración de desensamblador SWIFT</span><span class="sxs-lookup"><span data-stu-id="b02d1-121">SWIFT Disassembler Configuration Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)