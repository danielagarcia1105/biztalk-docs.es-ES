---
title: Texto SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, text
ms.assetid: 90851d38-7789-4b1b-813b-7943f77ab984
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c80d8ee0343cbf8ac96d57119ef198d623159b26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214524"
---
# <a name="swift-text"></a><span data-ttu-id="ae5fb-102">Texto SWIFT</span><span class="sxs-lookup"><span data-stu-id="ae5fb-102">SWIFT Text</span></span>
<span data-ttu-id="ae5fb-103">El texto del mensaje constituye la carga del mensaje (FIN) financiero y contiene todos los campos de datos excepto los campos que contienen el remitente, el receptor y el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-103">The message text makes up the payload of the financial (FIN) message, and contains all of the data fields except the fields containing the sender, receiver, and message type.</span></span> <span data-ttu-id="ae5fb-104">Estos tres campos se encuentran en la parte de encabezado.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-104">These three fields are contained in the header portion.</span></span> <span data-ttu-id="ae5fb-105">Algunos mensajes también contienen un encabezado de usuario opcionales, que también puede proporcionar información de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-105">Some messages also contain an optional User Header, which may also provide processing information.</span></span>  
  
 <span data-ttu-id="ae5fb-106">Cada carga de mensaje FIN está formada por una serie de campos de una secuencia definida.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-106">Each FIN message payload consists of a series of fields in a defined sequence.</span></span> <span data-ttu-id="ae5fb-107">Estos campos se ajustan a las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="ae5fb-107">These fields conform to the following rules:</span></span>  
  
-   <span data-ttu-id="ae5fb-108">Los campos pueden estar obligatorio u opcional dentro de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-108">The fields may be required or optional within the sequence.</span></span>  
  
-   <span data-ttu-id="ae5fb-109">Una secuencia puede contener secuencias secundarias y puede repetir una subsecuencia dentro de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-109">A sequence may contain subsequences, and a subsequence may repeat within a sequence.</span></span>  
  
-   <span data-ttu-id="ae5fb-110">Puede usar un campo en varios tipos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-110">You can use a field in several message types.</span></span>  
  
-   <span data-ttu-id="ae5fb-111">Dentro de un campo, puede haber elementos o subcampos.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-111">Within a field, there may be elements or subfields.</span></span> <span data-ttu-id="ae5fb-112">Un elemento o un subcampo puede ser comunes a varios campos.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-112">An element or subfield may be common to several fields.</span></span>  
  
-   <span data-ttu-id="ae5fb-113">Cada secuencia repetida se representa mediante un nodo de grupo.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-113">Each repeating sequence is represented by a group node.</span></span>  
  
-   <span data-ttu-id="ae5fb-114">Cada campo Sí habrá varios niveles nodal, cada uno de ellos se describe como un registro.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-114">Each field may itself have multiple nodal levels, each described as a record.</span></span>  
  
-   <span data-ttu-id="ae5fb-115">Un elemento de esquema representa sólo el subcampo de nivel más bajo.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-115">A schema element represents only the lowest level subfield.</span></span>  
  
-   <span data-ttu-id="ae5fb-116">Registros y elementos comunes se definen en el esquema de base y comunes, tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-116">Common records and elements are defined in the common and base schema, as described below.</span></span>  
  
-   <span data-ttu-id="ae5fb-117">Algunos campos se pueden representar en varios formatos (como campos de entidad).</span><span class="sxs-lookup"><span data-stu-id="ae5fb-117">Some fields may be represented in several formats (such as party fields).</span></span> <span data-ttu-id="ae5fb-118">Estos campos se definen como campos de elección en el esquema.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-118">Such fields are defined as choice fields in the schema.</span></span>  
  
 <span data-ttu-id="ae5fb-119">Algunos campos tienen una limitada a conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-119">Some fields have limited sets of values.</span></span> <span data-ttu-id="ae5fb-120">En su mayor parte, el esquema muestra estos valores.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-120">For the most part, the schema lists these values.</span></span> <span data-ttu-id="ae5fb-121">Definiciones de esquema también incluyen la validación del juego de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ae5fb-121">Schema definitions also include character set validation.</span></span>