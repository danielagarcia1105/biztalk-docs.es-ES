---
title: "Configuración de A4SWIFT usuarios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, user accounts
- creating, user accounts
- user accounts, creating
ms.assetid: 45dcbece-ec8d-410a-8320-79bfbc4c779d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79c3b63cd77bb34545f4c4093796310aa7720563
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a4swift-users"></a><span data-ttu-id="16793-102">Configuración de los usuarios de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="16793-102">Configuring A4SWIFT Users</span></span>
<span data-ttu-id="16793-103">Durante la instalación de [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], el programa de configuración de A4SWIFT crea perfiles de socios comerciales de forma predeterminada y contratos y registra el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="16793-103">During installation of [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], the A4SWIFT configuration program creates default trading partner profiles and agreements, and registers the BizTalk Server.</span></span> <span data-ttu-id="16793-104">A4SWIFT también crea bibliotecas de documentos usadas por el componente de reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="16793-104">A4SWIFT also creates document libraries used by the Message Repair and New Submission component.</span></span>  
  
 <span data-ttu-id="16793-105">A4SWIFT crea las siguientes carpetas de documentos durante la instalación:</span><span class="sxs-lookup"><span data-stu-id="16793-105">A4SWIFT creates the following document folders during installation:</span></span>  
  
-   <span data-ttu-id="16793-106">Biblioteca de documentos de bandeja de salida</span><span class="sxs-lookup"><span data-stu-id="16793-106">Outbox document library</span></span>  
  
-   <span data-ttu-id="16793-107">Biblioteca de documentos de plantillas</span><span class="sxs-lookup"><span data-stu-id="16793-107">Templates document library</span></span>  
  
-   <span data-ttu-id="16793-108">Biblioteca de documentos sin analizar</span><span class="sxs-lookup"><span data-stu-id="16793-108">Unparsed document library</span></span>  
  
-   <span data-ttu-id="16793-109">Nueva biblioteca de documentos de mensajes de SWIFT MT</span><span class="sxs-lookup"><span data-stu-id="16793-109">New SWIFT MT Message document library</span></span>  
  
-   <span data-ttu-id="16793-110">Nueva biblioteca de documentos de mensajes de SWIFT MX</span><span class="sxs-lookup"><span data-stu-id="16793-110">New SWIFT MX Messages document library</span></span>  
  
 <span data-ttu-id="16793-111">Para cada departamento creado, el Administrador de A4SWIFT debe establecer manualmente los grupos de sitio para los departamentos correspondientes y funciones definidas de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="16793-111">For each department created, the A4SWIFT Administrator must manually set up site groups for the corresponding departments and A4SWIFT defined roles.</span></span> <span data-ttu-id="16793-112">Cada departamento/rol tiene una bandeja de entrada que se crea automáticamente el Client(PWC) Web de perfil.</span><span class="sxs-lookup"><span data-stu-id="16793-112">Each department/role has an inbox created automatically by the Profile Web Client(PWC).</span></span>  
  
 <span data-ttu-id="16793-113">Después de completa el programa de configuración del programa de instalación de A4SWIFT, el Administrador de A4SWIFT configura los flujos de trabajo para cada departamento de la organización.</span><span class="sxs-lookup"><span data-stu-id="16793-113">After the A4SWIFT setup configuration program is completed, the A4SWIFT Administrator configures workflows for each department in the organization.</span></span> <span data-ttu-id="16793-114">Durante la configuración de la reparación de mensajes y nuevo envío, a través del cliente Web de perfil, se crean las bandejas de entrada correspondientes para cada combinación de departamento o el rol.</span><span class="sxs-lookup"><span data-stu-id="16793-114">During Message Repair and New Submission configuration, through the Profile Web Client, corresponding inboxes are created for each department/role combination.</span></span> <span data-ttu-id="16793-115">Por ejemplo, durante la configuración de PWC un administrador de A4SWIFT crea un departamento con el nombre de pagos y, a continuación, asigna los roles de creadores, talleres de reparación y aprobadores a un departamento denominado pagos.</span><span class="sxs-lookup"><span data-stu-id="16793-115">For example, during PWC configuration an A4SWIFT Administrator creates a department named Payments and then assigns the roles of Creators, Repairers, and Approvers to a department called Payments.</span></span> <span data-ttu-id="16793-116">Las bibliotecas de documentos en el sitio MRSR se crean con los nombres de la Bandeja de entrada, como se muestra en los ejemplos en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="16793-116">Document libraries on the MRSR site are created with the inbox names as shown in the examples in the following table:</span></span>  
  
|<span data-ttu-id="16793-117">Nombre de departamento</span><span class="sxs-lookup"><span data-stu-id="16793-117">Department name</span></span>|<span data-ttu-id="16793-118">Nombre de rol</span><span class="sxs-lookup"><span data-stu-id="16793-118">Role name</span></span>|<span data-ttu-id="16793-119">Nombre de la Bandeja de entrada</span><span class="sxs-lookup"><span data-stu-id="16793-119">Inbox name</span></span>|  
|---------------------|---------------|----------------|  
|<span data-ttu-id="16793-120">Pagos</span><span class="sxs-lookup"><span data-stu-id="16793-120">Payments</span></span>|<span data-ttu-id="16793-121">Creadores de</span><span class="sxs-lookup"><span data-stu-id="16793-121">Creators</span></span>|<span data-ttu-id="16793-122">Payments_Creator</span><span class="sxs-lookup"><span data-stu-id="16793-122">Payments_Creator</span></span>|  
|<span data-ttu-id="16793-123">Pagos</span><span class="sxs-lookup"><span data-stu-id="16793-123">Payments</span></span>|<span data-ttu-id="16793-124">Talleres de reparación</span><span class="sxs-lookup"><span data-stu-id="16793-124">Repairers</span></span>|<span data-ttu-id="16793-125">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="16793-125">Payments_Repairers</span></span>|  
|<span data-ttu-id="16793-126">Pagos</span><span class="sxs-lookup"><span data-stu-id="16793-126">Payments</span></span>|<span data-ttu-id="16793-127">Aprobadores</span><span class="sxs-lookup"><span data-stu-id="16793-127">Approvers</span></span>|<span data-ttu-id="16793-128">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="16793-128">Payments_Approvers</span></span>|