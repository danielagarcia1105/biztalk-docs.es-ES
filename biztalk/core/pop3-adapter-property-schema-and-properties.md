---
title: POP3 Propiedades y esquema de propiedades de adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, POP3 adapters
- Subject properties [POP3 adapters]
- Date properties [POP3 adapters]
- From properties [POP3 adapters]
- To properties [POP3 adapters]
- POP3 adapters, properties
- configuring [POP3 adapters], schemas
- configuring [POP3 adapters], properties
- CC properties [POP3 adapters]
- Headers properties [POP3 adapters]
- ReplyTo properties [POP3 adapters]
- DispositionNotificationTo properties [POP3 adapters]
ms.assetid: 7a10ae1f-dbcf-4c05-9a50-2503895960f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b976aba7161272ebdc65da2b5bcd2067c8cd3a5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264172"
---
# <a name="pop3-adapter-property-schema-and-properties"></a><span data-ttu-id="7e63c-102">POP3 Propiedades y esquema de propiedades de adaptador</span><span class="sxs-lookup"><span data-stu-id="7e63c-102">POP3 Adapter Property Schema and Properties</span></span>
<span data-ttu-id="7e63c-103">La tabla siguiente enumera las propiedades del esquema de propiedades del adaptador de POP3.</span><span class="sxs-lookup"><span data-stu-id="7e63c-103">The following table lists the properties in the POP3 adapter property schema.</span></span>  
  
 <span data-ttu-id="7e63c-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties</span><span class="sxs-lookup"><span data-stu-id="7e63c-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties</span></span>  
  
|<span data-ttu-id="7e63c-105">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7e63c-105">**Name**</span></span>|<span data-ttu-id="7e63c-106">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7e63c-106">**Type**</span></span>|<span data-ttu-id="7e63c-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="7e63c-107">**Description**</span></span>|  
|--------------|--------------|---------------------|  
|<span data-ttu-id="7e63c-108">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="7e63c-108">**Subject**</span></span>|<span data-ttu-id="7e63c-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e63c-109">xs:string</span></span>|<span data-ttu-id="7e63c-110">Especifica el contenido que aparece en el **asunto** encabezado del mensaje</span><span class="sxs-lookup"><span data-stu-id="7e63c-110">Specifies the content placed on the **Subject** header for the message</span></span>|  
|<span data-ttu-id="7e63c-111">**De**</span><span class="sxs-lookup"><span data-stu-id="7e63c-111">**From**</span></span>|<span data-ttu-id="7e63c-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e63c-112">xs:string</span></span>|<span data-ttu-id="7e63c-113">Especifica la dirección de correo electrónico que aparece en el **de** campo de encabezado de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e63c-113">Specifies the e-mail address placed on the **From** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="7e63c-114">**Para**</span><span class="sxs-lookup"><span data-stu-id="7e63c-114">**To**</span></span>|<span data-ttu-id="7e63c-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e63c-115">xs:string</span></span>|<span data-ttu-id="7e63c-116">Especifica la dirección de correo electrónico aparecen en la **a** campo de encabezado de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e63c-116">Specifies the e-mail address or addresses placed on the **To** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="7e63c-117">**ReplyTo**</span><span class="sxs-lookup"><span data-stu-id="7e63c-117">**ReplyTo**</span></span>|<span data-ttu-id="7e63c-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e63c-118">xs:string</span></span>|<span data-ttu-id="7e63c-119">Especifica la dirección de correo electrónico que aparece en el **ReplyTo** campo de encabezado de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e63c-119">Specifies the e-mail address placed on the **ReplyTo** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="7e63c-120">**CC**</span><span class="sxs-lookup"><span data-stu-id="7e63c-120">**CC**</span></span>|<span data-ttu-id="7e63c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e63c-121">xs:string</span></span>|<span data-ttu-id="7e63c-122">Especifica la dirección de correo electrónico aparecen en la **CC** campo de encabezado de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e63c-122">Specifies the e-mail address or addresses placed on the **CC** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="7e63c-123">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="7e63c-123">**Date**</span></span>|<span data-ttu-id="7e63c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e63c-124">xs:string</span></span>|<span data-ttu-id="7e63c-125">Especifica el contenido que aparece en el **fecha** campo de encabezado de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e63c-125">Specifies the content placed on the **Date** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="7e63c-126">**DispositionNotificationTo**</span><span class="sxs-lookup"><span data-stu-id="7e63c-126">**DispositionNotificationTo**</span></span>|<span data-ttu-id="7e63c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e63c-127">xs:string</span></span>|<span data-ttu-id="7e63c-128">Especifica el contenido que aparece en el **DispositionNotificationTo** campo de encabezado de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e63c-128">Specifies the content placed on the **DispositionNotificationTo** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="7e63c-129">**Encabezados**</span><span class="sxs-lookup"><span data-stu-id="7e63c-129">**Headers**</span></span>|<span data-ttu-id="7e63c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e63c-130">xs:string</span></span>|<span data-ttu-id="7e63c-131">Especifica el contenido de todos los campos de encabezado del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7e63c-131">Specifies the content of all of the header fields of the e-mail message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e63c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e63c-132">See Also</span></span>  
 [<span data-ttu-id="7e63c-133">Configurar el adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="7e63c-133">Configuring the POP3 Adapter</span></span>](../core/configuring-the-pop3-adapter.md)