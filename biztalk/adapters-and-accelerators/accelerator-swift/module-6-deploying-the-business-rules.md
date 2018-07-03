---
title: 'Módulo 6: Implementación de las reglas de negocio | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, deploying business rules
- deploying, business rules
- business rules
ms.assetid: e8fb8993-3450-4795-80fd-ff28bff8fe97
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 389d8038b5a216f90d85399eeefaebde86284c71
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972845"
---
# <a name="module-6-deploying-the-business-rules"></a><span data-ttu-id="0f47a-102">Módulo 6: Implementación de las reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="0f47a-102">Module 6: Deploying the Business Rules</span></span>
<span data-ttu-id="0f47a-103">En este módulo, implementar las reglas de negocios, confirme el registro de instalación y confirmar la implementación mediante la herramienta Compositor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="0f47a-103">In this module, you deploy the business rules, confirm your installation log, and confirm your deployment using the Business Rule Composer tool.</span></span>  
  
 <span data-ttu-id="0f47a-104">Usar reglas de negocios para asegurarse de que Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] mensajes cumplen con las especificaciones de formato, especificaciones de los campos y las reglas de red validado tal como se define en la sociedad de estándares de telecomunicaciones financieros entre bancos más (SWIFT) en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="0f47a-104">You use business rules to ensure that Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] messages adhere to format specifications, field specifications, and network validated rules as defined in the Society for Worldwide Interbank Financial Telecommunication (SWIFT) standards.</span></span> <span data-ttu-id="0f47a-105">Especificaciones de formato se refieren a la estructura del mensaje como un todo y cada campo en el mensaje de detalles de especificaciones de los campos.</span><span class="sxs-lookup"><span data-stu-id="0f47a-105">Format specifications pertain to the structure of the message as a whole and field specifications detail each field in the message.</span></span> <span data-ttu-id="0f47a-106">Las reglas de red validado se aplican a las validaciones de campos cruzados y son complejas por naturaleza.</span><span class="sxs-lookup"><span data-stu-id="0f47a-106">Network validated rules apply to cross-field validations and are complex in nature.</span></span>  
  
 <span data-ttu-id="0f47a-107">A4SWIFT proporciona especificaciones de esquema XSD para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="0f47a-107">A4SWIFT provides XSD schema specifications for each message.</span></span> <span data-ttu-id="0f47a-108">El Desensamblador de A4SWIFT (DASM) y de ensamblador (ASM) usan el esquema para analizar o serializar y validar los mensajes de archivo sin formato nativos.</span><span class="sxs-lookup"><span data-stu-id="0f47a-108">The A4SWIFT disassembler (DASM) and assembler (ASM) use the schema to parse or serialize and validate native flat-file messages.</span></span> <span data-ttu-id="0f47a-109">Las validaciones se limitan a las especificaciones de formato y especificaciones de los campos que codifica el esquema.</span><span class="sxs-lookup"><span data-stu-id="0f47a-109">Validations are limited to format specifications and field specifications that the schema encodes.</span></span> <span data-ttu-id="0f47a-110">Sin embargo, no puede codificar algunos formatos y reglas relacionadas están dentro del esquema de campo.</span><span class="sxs-lookup"><span data-stu-id="0f47a-110">However, you cannot encode some formats and field related rules within the schema.</span></span>  
  
 <span data-ttu-id="0f47a-111">A4SWIFT también incluye un conjunto de reglas de negocios que siga las guías de versión de estándares (SRG) de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0f47a-111">A4SWIFT also includes a set of business rules that follow the SWIFT Standards Release Guides (SRG).</span></span> <span data-ttu-id="0f47a-112">El motor de reglas de negocios (BRE) de BizTalk Server llama a las directivas de A4SWIFT y aplica las reglas de negocios de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0f47a-112">The BizTalk Server Business Rule Engine (BRE) calls the A4SWIFT policies and enforces the A4SWIFT business rules.</span></span>  
  
 <span data-ttu-id="0f47a-113">Estas reglas de negocios se incluyen debido a las complejas validaciones relativas a dar formato y los campos y reglas de red validado que superan la capacidad física del esquema.</span><span class="sxs-lookup"><span data-stu-id="0f47a-113">These business rules are included due to the complex validations relating to format and fields, and network-validated rules that are beyond the natural capability of the schema.</span></span> <span data-ttu-id="0f47a-114">Los componentes de SWIFT DASM o ASM dentro de una canalización de envío o recepción llaman el BRE.</span><span class="sxs-lookup"><span data-stu-id="0f47a-114">The SWIFT DASM or ASM components within a receive or send pipeline call the BRE.</span></span>  
  
 <span data-ttu-id="0f47a-115">Activar las validaciones o desactivar cambiando el **BREValidation** propiedad para el DASM dentro de la canalización.</span><span class="sxs-lookup"><span data-stu-id="0f47a-115">You turn the validations on or off by changing the **BREValidation** property for the DASM within your pipeline.</span></span>  
  
 <span data-ttu-id="0f47a-116">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="0f47a-116">This section contains:</span></span>  
  
-   [<span data-ttu-id="0f47a-117">Lección 1: Implementación de las reglas de negocio relacionadas</span><span class="sxs-lookup"><span data-stu-id="0f47a-117">Lesson 1: Deploying the Related Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)  
  
-   [<span data-ttu-id="0f47a-118">Lección 2: Confirmación de la implementación mediante la herramienta Compositor de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="0f47a-118">Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)