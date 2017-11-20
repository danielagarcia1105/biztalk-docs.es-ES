---
title: Elemento estructural de elemento de datos EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 775e8b87-b952-46d2-a506-5174d216a9aa
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600edb30ff157a520ac67eebce58428a62e27c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-data-element-structural-element"></a><span data-ttu-id="4aaa9-102">Elemento estructural de elemento de datos EDI</span><span class="sxs-lookup"><span data-stu-id="4aaa9-102">EDI Data Element Structural Element</span></span>
<span data-ttu-id="4aaa9-103">El elemento de datos es la unidad de datos principal del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4aaa9-103">The data element is the primary unit of data in the message.</span></span> <span data-ttu-id="4aaa9-104">Los elementos de datos se separan mediante el separador de elementos de datos, que es un asterisco de forma predeterminada para X12 y un signo más de manera predeterminada para EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="4aaa9-104">Data elements are separated by the data element separator, which is an asterisk by default for X12 and a plus sign by default for EDIFACT.</span></span> <span data-ttu-id="4aaa9-105">La opcionalidad de elementos de datos se define como obligatorio, opcional o condicional.</span><span class="sxs-lookup"><span data-stu-id="4aaa9-105">The optionality of data elements is defined as mandatory, optional, or conditional.</span></span>  
  
 <span data-ttu-id="4aaa9-106">Un elemento de datos puede ser simple o compuesto.</span><span class="sxs-lookup"><span data-stu-id="4aaa9-106">A data element can be either simple or composite.</span></span> <span data-ttu-id="4aaa9-107">Los elementos de datos simples son numéricos y forman el nivel mínimo de datos.</span><span class="sxs-lookup"><span data-stu-id="4aaa9-107">Simple data elements are numeric and are the lowest level of data.</span></span> <span data-ttu-id="4aaa9-108">Los elementos de datos compuestos son concatenaciones de subelementos, que son elementos de datos simples separados por un separador de componentes.</span><span class="sxs-lookup"><span data-stu-id="4aaa9-108">Composite data elements are concatenations of sub element, which are simple data elements separated by a component separator.</span></span> <span data-ttu-id="4aaa9-109">De forma predeterminada, el separador de componentes es el signo de dos puntos para X12 y EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="4aaa9-109">By default, the component separator is the colon for X12 and EDIFACT.</span></span>  
  
 <span data-ttu-id="4aaa9-110">Para mensajes codificados con EDIFACT, si los datos se van a enviar mediante EDI, es necesario enviar los caracteres definidos que se van a usar como separador. Debe usar un carácter de versión para indicar que el siguiente carácter no es un separador sino que forma parte de los datos.</span><span class="sxs-lookup"><span data-stu-id="4aaa9-110">For EDIFACT-encoded messages, if the data to be sent via EDI needs to send any character defined for use as a separator, you need to use a release character to indicate that the following character is not a separator, but is part of the data.</span></span> <span data-ttu-id="4aaa9-111">De forma predeterminada, el carácter de versión es el signo de interrogación de cierre (?).</span><span class="sxs-lookup"><span data-stu-id="4aaa9-111">The release character is by default the question mark (?).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4aaa9-112">No se admite un carácter de versión para X12.</span><span class="sxs-lookup"><span data-stu-id="4aaa9-112">A release character is not supported for X12.</span></span> <span data-ttu-id="4aaa9-113">Si se encuentra un separador como parte de los datos de un intercambio codificado con X12, ya sea en la recepción o en el envío, el intercambio se suspenderá.</span><span class="sxs-lookup"><span data-stu-id="4aaa9-113">If a separator is encountered as part of the data of an X12-encoded interchange, on either the receive or send side, the interchange will be suspended.</span></span>