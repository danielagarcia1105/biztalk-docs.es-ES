---
title: POP3 Adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- POP3 adapters, about POP3 adapters
- authenticating, POP3 adapters
- POP3 adapters
- POP3 adapters, receive adapters
- POP3 adapters, authenticating
- receive adapters, POP3 adapters
ms.assetid: 008f7fa7-60c3-4ea3-b90d-821e4029a04c
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbe21a3cf0e611a690cf22c88b1344926fa72744
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="pop3-adapter"></a><span data-ttu-id="42f5e-102">Adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="42f5e-102">POP3 Adapter</span></span>
<span data-ttu-id="42f5e-103">El adaptador de Protocolo de oficina de correos v. 3 (POP3) se utiliza para recuperar datos de un servidor que aloja buzones POP3 a un servidor en el que se ejecuta Microsoft BizTalk Server mediante el protocolo POP3.</span><span class="sxs-lookup"><span data-stu-id="42f5e-103">You use the Post Office Protocol 3 (POP3) adapter to retrieve data from a server that houses POP3 mailboxes into a server running Microsoft BizTalk Server by means of the POP3 protocol.</span></span>  
  
 <span data-ttu-id="42f5e-104">El adaptador de POP3 se compone de un solo adaptador: un adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="42f5e-104">The POP3 adapter consists of only one adapter, a receive adapter.</span></span> <span data-ttu-id="42f5e-105">El adaptador de recepción controla las ubicaciones de recepción que utilizan el adaptador de POP3.</span><span class="sxs-lookup"><span data-stu-id="42f5e-105">The receive adapter controls the receive locations that use the POP3 adapter.</span></span>  
  
 <span data-ttu-id="42f5e-106">En este tema se analiza el flujo de trabajo del adaptador de recepción POP3.</span><span class="sxs-lookup"><span data-stu-id="42f5e-106">This topic discusses the workflow of the POP3 receive adapter.</span></span>  
  
 <span data-ttu-id="42f5e-107">**POP3 Adaptador de recepción**</span><span class="sxs-lookup"><span data-stu-id="42f5e-107">**POP3 Receive Adapter**</span></span>  
  
 <span data-ttu-id="42f5e-108">El adaptador de recepción POP3 recupera el correo electrónico de un buzón definido de un servidor POP3 especificado.</span><span class="sxs-lookup"><span data-stu-id="42f5e-108">The POP3 receive adapter retrieves e-mail from a specified mailbox on a specified POP3 server.</span></span> <span data-ttu-id="42f5e-109">De forma predeterminada, el adaptador de recepción POP3 aplica el procesamiento de MIME a los mensajes de correo electrónico que descarga y los envía a BizTalk Server como mensajes de varias partes de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="42f5e-109">By default, the POP3 receive adapter applies MIME processing to the e-mail messages that it downloads and submits these messages to BizTalk Server as multipart BizTalk messages.</span></span> <span data-ttu-id="42f5e-110">El adaptador de recepción POP3 puede recibir mensajes de correo electrónico y procesarlos en los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="42f5e-110">The POP3 receive adapter can receive and process e-mail in the following formats:</span></span>  
  
-   <span data-ttu-id="42f5e-111">Texto sin formato</span><span class="sxs-lookup"><span data-stu-id="42f5e-111">Plain text</span></span>  
  
-   <span data-ttu-id="42f5e-112">Con codificación MIME</span><span class="sxs-lookup"><span data-stu-id="42f5e-112">MIME encoded</span></span>  
  
-   <span data-ttu-id="42f5e-113">Con cifrado MIME</span><span class="sxs-lookup"><span data-stu-id="42f5e-113">MIME encrypted</span></span>  
  
-   <span data-ttu-id="42f5e-114">Con firma y con codificación MIME</span><span class="sxs-lookup"><span data-stu-id="42f5e-114">MIME encoded and signed</span></span>  
  
-   <span data-ttu-id="42f5e-115">Con firma y con cifrado MIME</span><span class="sxs-lookup"><span data-stu-id="42f5e-115">MIME encrypted and signed</span></span>  
  
 <span data-ttu-id="42f5e-116">**Procesamiento por lotes de soporte técnico para el adaptador de recepción POP3**</span><span class="sxs-lookup"><span data-stu-id="42f5e-116">**Batching Support for the POP3 Receive Adapter**</span></span>  
  
 <span data-ttu-id="42f5e-117">El adaptador de recepción POP3 no admite el procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="42f5e-117">The POP3 receive adapter does not support batching.</span></span>  
  
 <span data-ttu-id="42f5e-118">**Autenticación con servidor POP3**</span><span class="sxs-lookup"><span data-stu-id="42f5e-118">**Authentication with POP3 Server**</span></span>  
  
 <span data-ttu-id="42f5e-119">Se admiten los siguientes métodos de autenticación para su uso con el adaptador de POP3:</span><span class="sxs-lookup"><span data-stu-id="42f5e-119">The following authentication methods are supported for use with the POP3 adapter:</span></span>  
  
-   <span data-ttu-id="42f5e-120">**Básica.**</span><span class="sxs-lookup"><span data-stu-id="42f5e-120">**Basic.**</span></span> <span data-ttu-id="42f5e-121">El servidor POP3 utiliza credenciales proporcionadas por el usuario para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="42f5e-121">The POP3 server uses user provided credentials for authentication.</span></span>  <span data-ttu-id="42f5e-122">Estas credenciales se envían en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="42f5e-122">These credentials are sent in clear text.</span></span>  
  
-   <span data-ttu-id="42f5e-123">**Implícito (APOP).**</span><span class="sxs-lookup"><span data-stu-id="42f5e-123">**Digest (APOP).**</span></span> <span data-ttu-id="42f5e-124">El servidor POP3 utiliza una cadena implícita para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="42f5e-124">The POP3 server uses a digest string for authentication.</span></span>  
  
-   <span data-ttu-id="42f5e-125">**Autenticación de contraseña segura (SPA).**</span><span class="sxs-lookup"><span data-stu-id="42f5e-125">**Secure Password Authentication (SPA).**</span></span> <span data-ttu-id="42f5e-126">El servidor POP3 utiliza credenciales del proceso actual para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="42f5e-126">The POP3 server uses current process credentials for authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="42f5e-127">En esta sección</span><span class="sxs-lookup"><span data-stu-id="42f5e-127">In This Section</span></span>  
  
-   [<span data-ttu-id="42f5e-128">¿Qué es el adaptador de POP3?</span><span class="sxs-lookup"><span data-stu-id="42f5e-128">What Is the POP3 Adapter?</span></span>](../core/what-is-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="42f5e-129">Configurar el adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="42f5e-129">Configuring the POP3 Adapter</span></span>](../core/configuring-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="42f5e-130">Tutorial: Crear una aplicación de BizTalk que usa el adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="42f5e-130">Walkthrough: Creating a BizTalk Application That Uses the POP3 Adapter</span></span>](../core/walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="42f5e-131">Procesar mensajes de varias partes con el adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="42f5e-131">Processing Multi Part Messages with the POP3 Adapter</span></span>](../core/processing-multi-part-messages-with-the-pop3-adapter.md)