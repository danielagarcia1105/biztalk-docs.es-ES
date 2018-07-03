---
title: Trabajar con esquemas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, schemas
- schemas, developing
ms.assetid: 123c4b43-34e4-41c7-980d-5d518b1479c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb6ac17cd0959d712da290b937a961d517f320e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968365"
---
# <a name="working-with-schemas"></a><span data-ttu-id="ad2ed-102">Trabajar con esquemas</span><span class="sxs-lookup"><span data-stu-id="ad2ed-102">Working with Schemas</span></span>
<span data-ttu-id="ad2ed-103">Los esquemas proporcionados en Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] son la representación XSD Microsoft de la sociedad para mensajes FIN de telecomunicaciones financieros entre bancos más (SWIFT) en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-103">The schemas provided in Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] are the Microsoft XSD representation of the Society for Worldwide Interbank Financial Telecommunication (SWIFT) FIN messages.</span></span> <span data-ttu-id="ad2ed-104">Cada tipo de mensaje tiene su propio esquema, incluidos los encabezados de SWIFT y finalizador SWIFT (formato de intercambio).</span><span class="sxs-lookup"><span data-stu-id="ad2ed-104">Each message type has its own schema, including the SWIFT header and SWIFT trailer (interchange format).</span></span> <span data-ttu-id="ad2ed-105">Este esquema es suficiente para enviar o recibir un mensaje SWIFT.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-105">This schema is sufficient to send or receive a SWIFT message.</span></span> <span data-ttu-id="ad2ed-106">Estos esquemas son una combinación única de registros delimitados y posicionales, que proporciona una representación XML detallada de las estructuras FIN de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-106">These schemas are a unique mixture of delimited and positional records, providing a detailed XML representation of the flat-file FIN structures.</span></span>  

 <span data-ttu-id="ad2ed-107">La mayoría de los clientes SWIFT usan un subconjunto relativamente pequeño de los mensajes de FIN de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-107">Most SWIFT customers use a relatively small subset of the SWIFT FIN messages.</span></span> <span data-ttu-id="ad2ed-108">Para implementar una solución para estos clientes, puede crear un proyecto de esquema de BizTalk (como se muestra en [módulo 2: agregar un nuevo proyecto de esquemas](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md) del tutorial de A4SWIFT).</span><span class="sxs-lookup"><span data-stu-id="ad2ed-108">To implement a solution for these customers, you can create a BizTalk schema project (as demonstrated in [Module 2: Adding a New Schemas Project](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md) of the A4SWIFT tutorial).</span></span> <span data-ttu-id="ad2ed-109">Agregue los esquemas de mensaje relevante (MT*xxx*.xsd) de \\\ programa Files\Microsoft BizTalk Accelerator para SWIFT \<versión\> MessagePack\SWIFT Messages\A4SWIFT-SRG\< versión\>\Category x\MT xyy directorio, donde x es el primer dígito del tipo de mensaje FIN y xyy es el tipo de mensaje de tres dígitos para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-109">Add the relevant message schemas (MT*xxx*.xsd) from \\\ Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> MessagePack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category x\MT xyy directory, where x is the first digit of the FIN message type and xyy is the three-digit message type for the message.</span></span>  

 <span data-ttu-id="ad2ed-110">Puede agregar varios esquemas para el mismo proyecto.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-110">You can add several schemas to the same project.</span></span> <span data-ttu-id="ad2ed-111">Para mantener la capacidad de administración, no debe agregar más de 20 esquemas de mensaje por proyecto.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-111">To maintain manageability, you should not add more than 20 message schemas per project.</span></span> <span data-ttu-id="ad2ed-112">También deberá agregar los esquemas de bases y comunes para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-112">You also need to add the base and common schemas to the project.</span></span> <span data-ttu-id="ad2ed-113">Si ya ha implementado los esquemas de bases y comunes, deberá hacer referencia a su ensamblado, en lugar de implementarlos.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-113">If you have already deployed the base and common schemas, you need to make a reference to their assembly, rather than deploy them.</span></span> <span data-ttu-id="ad2ed-114">Esta sección describen estos esquemas.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-114">This section describes these schemas.</span></span> <span data-ttu-id="ad2ed-115">Los esquemas de mensaje están listos usarlos tal cual para los mensajes enviados a la red SWIFT y los mensajes recibidos de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-115">The message schemas are ready to use as is for both messages sent to the SWIFT network and messages received from SWIFT.</span></span>  

 <span data-ttu-id="ad2ed-116">Puede examinar el contenido de cada esquema SWIFT de Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] mediante el Editor de esquemas.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-116">You can examine the contents of each SWIFT schema in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] using the Schema Editor.</span></span> <span data-ttu-id="ad2ed-117">Todos los esquemas de intercambio de mensajes tienen la siguiente estructura común:</span><span class="sxs-lookup"><span data-stu-id="ad2ed-117">All of the message interchange schemas have the following common structure:</span></span>  

- <span data-ttu-id="ad2ed-118">Encabezados</span><span class="sxs-lookup"><span data-stu-id="ad2ed-118">Headers</span></span>  

- <span data-ttu-id="ad2ed-119">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ad2ed-119">Message text</span></span>  

- <span data-ttu-id="ad2ed-120">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="ad2ed-120">Trailers</span></span>  

  <span data-ttu-id="ad2ed-121">En esta sección se describe los esquemas de encabezado y finalizador.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-121">This section describes the header and trailer schemas.</span></span> <span data-ttu-id="ad2ed-122">El texto del mensaje consta de la carga del mensaje FIN y contiene todos los campos de datos, excepto los campos que contienen el remitente, el receptor y el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-122">The message text comprises the payload of the FIN message, and contains all of the data fields except the fields containing the sender, receiver, and message type.</span></span> <span data-ttu-id="ad2ed-123">Estos tres campos se encuentran en la parte de encabezado.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-123">These three fields are contained in the header portion.</span></span> <span data-ttu-id="ad2ed-124">Algunos mensajes contienen también un encabezado opcional del usuario, que también puede proporcionar información de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-124">Some messages also contain an optional user header, which may also provide processing information.</span></span>  

  <span data-ttu-id="ad2ed-125">Cada carga de mensaje FIN consta de una serie de campos de una secuencia definida.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-125">Each FIN message payload consists of a series of fields in a defined sequence.</span></span> <span data-ttu-id="ad2ed-126">Estos campos se ajustan a las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad2ed-126">These fields conform to the following rules:</span></span>  

- <span data-ttu-id="ad2ed-127">Los campos pueden ser obligatorio u opcional dentro de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-127">The fields may be required or optional within the sequence.</span></span>  

- <span data-ttu-id="ad2ed-128">Una secuencia puede contener las secuencias secundarias, y puede que se repita una subsecuencia dentro de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-128">A sequence may contain sub-sequences, and a sub-sequence may repeat within a sequence.</span></span>  

- <span data-ttu-id="ad2ed-129">Puede usar un campo en varios tipos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-129">You can use a field in several message types.</span></span>  

- <span data-ttu-id="ad2ed-130">Dentro de un campo, puede haber elementos o subcampos.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-130">Within a field, there may be elements or subfields.</span></span> <span data-ttu-id="ad2ed-131">Un elemento o subcampo puede ser comunes a varios campos.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-131">An element or subfield may be common to several fields.</span></span>  

- <span data-ttu-id="ad2ed-132">Un nodo de grupo representa cada secuencia repetida.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-132">A group node represents each repeating sequence.</span></span>  

- <span data-ttu-id="ad2ed-133">Cada campo puede tener varios niveles nodal, describe cada uno como un registro.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-133">Each field may itself have multiple nodal levels, each described as a record.</span></span>  

- <span data-ttu-id="ad2ed-134">Elementos de esquema representan sólo los subcampos de nivel más bajo.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-134">Schema elements represent only the lowest level subfields.</span></span>  

- <span data-ttu-id="ad2ed-135">Los esquemas de bases y comunes definen registros y los elementos comunes.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-135">The common and base schemas define common records and elements.</span></span>  

- <span data-ttu-id="ad2ed-136">Los esquemas representan algunos campos en varios formatos (por ejemplo, los campos de entidad).</span><span class="sxs-lookup"><span data-stu-id="ad2ed-136">Schemas represent some fields in several formats (such as party fields).</span></span> <span data-ttu-id="ad2ed-137">Los esquemas definen esos campos como campos de elección.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-137">Schemas define such fields as choice fields.</span></span>  

- <span data-ttu-id="ad2ed-138">Algunos campos tienen una limitada de conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-138">Some fields have limited sets of values.</span></span> <span data-ttu-id="ad2ed-139">En su mayor parte, el esquema muestra estos valores.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-139">For the most part, the schema lists these values.</span></span> <span data-ttu-id="ad2ed-140">Definiciones de esquema también incluyen la validación del juego de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ad2ed-140">Schema definitions also include character set validation.</span></span>  

  <span data-ttu-id="ad2ed-141">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="ad2ed-141">This section contains:</span></span>  

- [<span data-ttu-id="ad2ed-142">Esquemas base y comunes</span><span class="sxs-lookup"><span data-stu-id="ad2ed-142">Base and Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/base-and-common-schemas.md)  

- [<span data-ttu-id="ad2ed-143">Esquemas de finalizadores y encabezados de SWIFT</span><span class="sxs-lookup"><span data-stu-id="ad2ed-143">SWIFT Header and Trailer Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  

- [<span data-ttu-id="ad2ed-144">Convenciones de nomenclatura de esquemas de SWIFT</span><span class="sxs-lookup"><span data-stu-id="ad2ed-144">SWIFT Schema Naming Conventions</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-schema-naming-conventions.md)
