---
title: Texto de SWIFT | Microsoft Docs
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
ms.openlocfilehash: 06e46c8be5da2f62f2b59ce2591e0559367adf08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990933"
---
# <a name="swift-text"></a><span data-ttu-id="5da39-102">Texto de SWIFT</span><span class="sxs-lookup"><span data-stu-id="5da39-102">SWIFT Text</span></span>
<span data-ttu-id="5da39-103">El texto del mensaje conforma la carga del mensaje (FIN) financiero y contiene todos los campos de datos, excepto los campos que contienen el remitente, el receptor y el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5da39-103">The message text makes up the payload of the financial (FIN) message, and contains all of the data fields except the fields containing the sender, receiver, and message type.</span></span> <span data-ttu-id="5da39-104">Estos tres campos se encuentran en la parte de encabezado.</span><span class="sxs-lookup"><span data-stu-id="5da39-104">These three fields are contained in the header portion.</span></span> <span data-ttu-id="5da39-105">Algunos mensajes contienen también un encabezado de usuario opcional, que también puede proporcionar información de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5da39-105">Some messages also contain an optional User Header, which may also provide processing information.</span></span>  
  
 <span data-ttu-id="5da39-106">Cada carga de mensaje FIN consta de una serie de campos de una secuencia definida.</span><span class="sxs-lookup"><span data-stu-id="5da39-106">Each FIN message payload consists of a series of fields in a defined sequence.</span></span> <span data-ttu-id="5da39-107">Estos campos se ajustan a las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5da39-107">These fields conform to the following rules:</span></span>  
  
- <span data-ttu-id="5da39-108">Los campos pueden ser obligatorio u opcional dentro de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="5da39-108">The fields may be required or optional within the sequence.</span></span>  
  
- <span data-ttu-id="5da39-109">Una secuencia puede contener subsecuencias, y puede que se repita una subsecuencia dentro de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="5da39-109">A sequence may contain subsequences, and a subsequence may repeat within a sequence.</span></span>  
  
- <span data-ttu-id="5da39-110">Puede usar un campo en varios tipos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5da39-110">You can use a field in several message types.</span></span>  
  
- <span data-ttu-id="5da39-111">Dentro de un campo, puede haber elementos o subcampos.</span><span class="sxs-lookup"><span data-stu-id="5da39-111">Within a field, there may be elements or subfields.</span></span> <span data-ttu-id="5da39-112">Un elemento o subcampo puede ser comunes a varios campos.</span><span class="sxs-lookup"><span data-stu-id="5da39-112">An element or subfield may be common to several fields.</span></span>  
  
- <span data-ttu-id="5da39-113">Cada secuencia repetida se representa mediante un nodo de grupo.</span><span class="sxs-lookup"><span data-stu-id="5da39-113">Each repeating sequence is represented by a group node.</span></span>  
  
- <span data-ttu-id="5da39-114">Cada campo puede tener varios niveles nodal, describe cada uno como un registro.</span><span class="sxs-lookup"><span data-stu-id="5da39-114">Each field may itself have multiple nodal levels, each described as a record.</span></span>  
  
- <span data-ttu-id="5da39-115">Un elemento de esquema representa sólo el subcampo de nivel más bajo.</span><span class="sxs-lookup"><span data-stu-id="5da39-115">A schema element represents only the lowest level subfield.</span></span>  
  
- <span data-ttu-id="5da39-116">Registros y los elementos comunes se definen en el esquema de base y comunes, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="5da39-116">Common records and elements are defined in the common and base schema, as described below.</span></span>  
  
- <span data-ttu-id="5da39-117">Algunos campos se pueden representar en varios formatos (por ejemplo, los campos de entidad).</span><span class="sxs-lookup"><span data-stu-id="5da39-117">Some fields may be represented in several formats (such as party fields).</span></span> <span data-ttu-id="5da39-118">Estos campos se definen como campos de elección en el esquema.</span><span class="sxs-lookup"><span data-stu-id="5da39-118">Such fields are defined as choice fields in the schema.</span></span>  
  
  <span data-ttu-id="5da39-119">Algunos campos tienen una limitada de conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="5da39-119">Some fields have limited sets of values.</span></span> <span data-ttu-id="5da39-120">En su mayor parte, el esquema muestra estos valores.</span><span class="sxs-lookup"><span data-stu-id="5da39-120">For the most part, the schema lists these values.</span></span> <span data-ttu-id="5da39-121">Definiciones de esquema también incluyen la validación del juego de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5da39-121">Schema definitions also include character set validation.</span></span>