---
title: Restricciones en el protocolo SMTP a la propiedad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: c876d30e-44ab-462d-8c98-64416ed6dd1f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b59495ac94b3591801101607533eb9c7dba158fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268340"
---
# <a name="restrictions-on-the-smtp-to-property"></a><span data-ttu-id="da8d0-102">Restricciones en el protocolo SMTP a la propiedad</span><span class="sxs-lookup"><span data-stu-id="da8d0-102">Restrictions on the SMTP To Property</span></span>
<span data-ttu-id="da8d0-103">El **a** propiedad es una cadena que especifica la dirección SMTP del destinatario del mensaje.</span><span class="sxs-lookup"><span data-stu-id="da8d0-103">The **To** property is a string that specifies the SMTP address of the recipient of the message.</span></span> <span data-ttu-id="da8d0-104">Puede incluir varias direcciones con un separador admitido por el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="da8d0-104">You can list several addresses with a separator that SMTP server supports.</span></span>  
  
 <span data-ttu-id="da8d0-105">No hay restricciones específicas de formato en las direcciones SMTP.</span><span class="sxs-lookup"><span data-stu-id="da8d0-105">There are no specific restrictions for the format of an SMTP address.</span></span> <span data-ttu-id="da8d0-106">Esto significa que el adaptador aceptará cualquier formato admitido por un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="da8d0-106">This means that the adapter will accept any format that an SMTP server supports.</span></span> <span data-ttu-id="da8d0-107">Si un usuario proporciona direcciones que no son válidas, la operación de envío fallará, y el adaptador de envío SMTP informará de un error.</span><span class="sxs-lookup"><span data-stu-id="da8d0-107">If a user provides addresses that are not valid, the send operation will fail and the SMTP send adapter will report an error.</span></span>  
  
 <span data-ttu-id="da8d0-108">Las únicas restricciones para esta propiedad son que no puede dejarse en blanco y que no puede contener más de 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="da8d0-108">The only restrictions for this property are that it must not be empty and its size must not exceed 256 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da8d0-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="da8d0-109">See Also</span></span>  
 [<span data-ttu-id="da8d0-110">Restricciones al configurar el adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="da8d0-110">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)