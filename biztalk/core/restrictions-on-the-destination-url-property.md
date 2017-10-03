---
title: "Restricciones de la propiedad de dirección URL de destino | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [HTTP adapters], restrictions
- HTTP adapters, restrictions
ms.assetid: 982a5122-e43d-4730-a8b9-ceb1ff88638c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0788b693027fb803b121b1b732cb3ee126897e7b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="restrictions-on-the-destination-url-property"></a><span data-ttu-id="3b36c-102">Restricciones de la propiedad de dirección URL de destino</span><span class="sxs-lookup"><span data-stu-id="3b36c-102">Restrictions on the Destination URL Property</span></span>
<span data-ttu-id="3b36c-103">La dirección URL de destino es una cadena que especifica la dirección del servidor HTTP donde desea enviar mensajes con el protocolo HTTP.</span><span class="sxs-lookup"><span data-stu-id="3b36c-103">The destination URL is a string that specifies the address of the HTTP server where you want to send messages using the HTTP protocol.</span></span>  
  
 <span data-ttu-id="3b36c-104">Las reglas y restricciones siguientes se aplican a la propiedad Dirección URL de destino:</span><span class="sxs-lookup"><span data-stu-id="3b36c-104">The following rules and restrictions apply to the destination URL property:</span></span>  
  
-   <span data-ttu-id="3b36c-105">Siempre debe especificar la propiedad Dirección URL de destino con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="3b36c-105">You must always specify the destination URL property in the following format:</span></span>  
  
     <span data-ttu-id="3b36c-106">http [s] ://\<host > [:\<puerto >] [/\<ruta de acceso > [/\<archivo > [?\< cadena de consulta >]]]</span><span class="sxs-lookup"><span data-stu-id="3b36c-106">http[s]://\<host>[:\<port>][/\<path>[/\<file>[?\<query-string>]]]</span></span>  
  
-   <span data-ttu-id="3b36c-107">La cadena entera puede estar o no codificada con un URI.</span><span class="sxs-lookup"><span data-stu-id="3b36c-107">The whole string may or may not be URI encoded.</span></span>  
  
-   <span data-ttu-id="3b36c-108">Toda la cadena, excepto la cadena de consulta, no puede contener ninguno de los siguientes caracteres: \< >: \ &#124; " ?</span><span class="sxs-lookup"><span data-stu-id="3b36c-108">The whole string, except the query string, cannot contain any of the following characters: \< > : \ &#124; " ?</span></span> <span data-ttu-id="3b36c-109">*.</span><span class="sxs-lookup"><span data-stu-id="3b36c-109">*.</span></span>  
  
-   <span data-ttu-id="3b36c-110">La propiedad no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3b36c-110">The property is not case-sensitive.</span></span>  
  
-   <span data-ttu-id="3b36c-111">La longitud de la cadena no debe exceder 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3b36c-111">The length of the string must not exceed 256 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b36c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b36c-112">See Also</span></span>  
 [<span data-ttu-id="3b36c-113">Configurar un puerto de envío HTTP</span><span class="sxs-lookup"><span data-stu-id="3b36c-113">Configuring an HTTP Send Port</span></span>](../core/configuring-an-http-send-port.md)