---
title: No se admite porque la información de codificación de UNB1.1 no coincide con la codificación real del juego de caracteres | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 085ea8e3-e0d8-45bd-9985-6787b00e4d5a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41a6eafbb0e71de5f13e792361cdc0d1fc338088
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239908"
---
# <a name="character-set-not-supported-because-the-encoding-information-in-unb11-does-not-match-the-actual-encoding"></a><span data-ttu-id="2f440-102">Juego de caracteres no admitido porque la información de codificación de UNB1.1 no coincide con la codificación real del intercambio</span><span class="sxs-lookup"><span data-stu-id="2f440-102">Character set not supported because the encoding information in UNB1.1 does not match the actual encoding</span></span>
## <a name="details"></a><span data-ttu-id="2f440-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2f440-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f440-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2f440-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2f440-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2f440-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2f440-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2f440-106">Event ID</span></span>|-|  
|<span data-ttu-id="2f440-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2f440-107">Event Source</span></span>|<span data-ttu-id="2f440-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f440-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="2f440-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2f440-109">Component</span></span>|<span data-ttu-id="2f440-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="2f440-110">EDI Engine</span></span>|  
|<span data-ttu-id="2f440-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2f440-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="2f440-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2f440-112">Message Text</span></span>|<span data-ttu-id="2f440-113">Juego de caracteres no admitido.</span><span class="sxs-lookup"><span data-stu-id="2f440-113">Character set not supported.</span></span> <span data-ttu-id="2f440-114">Podría deberse a que la información de codificación de UNB1.1 no coincide con la codificación real del intercambio.</span><span class="sxs-lookup"><span data-stu-id="2f440-114">It could be due to the fact that encoding information in UNB1.1 does not match the actual encoding of the interchange.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2f440-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="2f440-115">Explanation</span></span>  
 <span data-ttu-id="2f440-116">Este evento de error,  indica que la canalización de recepción EDI no pudo procesar el intercambio EDIFACT entrante porque los caracteres usados en el intercambio no se ajustaban al conjunto de caracteres identificados en el campo UNB1.1 del intercambio.</span><span class="sxs-lookup"><span data-stu-id="2f440-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the characters used in the interchange did not conform to the character set identified in field UNB1.1 of the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2f440-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2f440-117">User Action</span></span>  
 <span data-ttu-id="2f440-118">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2f440-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="2f440-119">Cambie los caracteres usados en el intercambio de modo que se ajusten al conjunto de caracteres especificado en el campo UNB1.1 del intercambio.</span><span class="sxs-lookup"><span data-stu-id="2f440-119">Change the characters used in the interchange so they conform to the character set specified in field UNB1.1 of the interchange.</span></span>  
  
-   <span data-ttu-id="2f440-120">Cambie el conjunto de caracteres especificado en el campo UNB1.1 del intercambio de modo que todos los caracteres del intercambio formen parte del conjunto de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2f440-120">Change the character set specified in field UNB1.1 of the interchange, so all characters in the interchange are part of the character set.</span></span>