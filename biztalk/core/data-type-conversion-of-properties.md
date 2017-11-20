---
title: "Conversión de propiedades de tipos de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, data type conversion
- MQBYTE property [MQSeries adapters]
- MQLONG property [MQSeries adapters]
- MQCHAR property [MQSeries adapters]
- configuring [MQSeries adapters], data type conversion
ms.assetid: 5b81eab0-f7a1-42f3-b212-a211b2893fd5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3705f1d0a20a48f0683a15588891ef3fe60889cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-conversion-of-properties"></a><span data-ttu-id="f9ee4-102">Conversión de tipos de datos de propiedades</span><span class="sxs-lookup"><span data-stu-id="f9ee4-102">Data Type Conversion of Properties</span></span>
<span data-ttu-id="f9ee4-103">Las propiedades de encabezado de los mensajes MQSeries son estructuras de datos contenidas en el propio mensaje.</span><span class="sxs-lookup"><span data-stu-id="f9ee4-103">Header properties in an MQSeries message are data structures contained in the message itself.</span></span> <span data-ttu-id="f9ee4-104">Al enviar y recibir mensajes, el adaptador de MQSeries automáticamente valida y convierte determinados valores de los encabezados de mensaje MQSeries.</span><span class="sxs-lookup"><span data-stu-id="f9ee4-104">The MQSeries adapter automatically validates and converts certain values in MQSeries message headers when sending and receiving messages.</span></span>  
  
 <span data-ttu-id="f9ee4-105">En la tabla siguiente se describen los tipos de datos MQSeries, su validación y su conversión.</span><span class="sxs-lookup"><span data-stu-id="f9ee4-105">The following table describes the MQSeries data types and their validation and conversion.</span></span>  
  
|<span data-ttu-id="f9ee4-106">Tipo de datos MQSeries</span><span class="sxs-lookup"><span data-stu-id="f9ee4-106">MQSeries data type</span></span>|<span data-ttu-id="f9ee4-107">Validación y conversión</span><span class="sxs-lookup"><span data-stu-id="f9ee4-107">Validation and conversion</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="f9ee4-108">MQLONG</span><span class="sxs-lookup"><span data-stu-id="f9ee4-108">MQLONG</span></span>|<span data-ttu-id="f9ee4-109">MQSeries realiza la validación.</span><span class="sxs-lookup"><span data-stu-id="f9ee4-109">MQSeries performs the validation.</span></span> <span data-ttu-id="f9ee4-110">Realiza la conversión a un valor de tipo “entero largo”.</span><span class="sxs-lookup"><span data-stu-id="f9ee4-110">Converts to a long integer.</span></span> <span data-ttu-id="f9ee4-111">Los valores no válidos evitan que el mensaje se coloque en la cola MQSeries.</span><span class="sxs-lookup"><span data-stu-id="f9ee4-111">Values that are not valid prevent the message from going to the MQSeries queue.</span></span>|  
|<span data-ttu-id="f9ee4-112">MQCHAR</span><span class="sxs-lookup"><span data-stu-id="f9ee4-112">MQCHAR</span></span>|<span data-ttu-id="f9ee4-113">Realiza la conversión a una cadena.</span><span class="sxs-lookup"><span data-stu-id="f9ee4-113">Converts to a string.</span></span>|  
|<span data-ttu-id="f9ee4-114">MQBYTE</span><span class="sxs-lookup"><span data-stu-id="f9ee4-114">MQBYTE</span></span>|<span data-ttu-id="f9ee4-115">Realiza la conversión a una cadena que contiene los caracteres 0-9, a-f o A-F, que representan el valor hexadecimal del número.</span><span class="sxs-lookup"><span data-stu-id="f9ee4-115">Converts to a string that contains the characters 0-9 and a-f or A-F, representing the hexadecimal value of the number.</span></span>|  
  
 <span data-ttu-id="f9ee4-116">Muchas de las propiedades de MQSeries son valores enteros de 32 bits (4 bytes) sin signo.</span><span class="sxs-lookup"><span data-stu-id="f9ee4-116">Many of the MQSeries properties are 32-bit (4-byte) unsigned integers.</span></span> <span data-ttu-id="f9ee4-117">Dado que **uint** no es un Common Language Specification (CLS)-tipo compatible, debe asignar a **objeto** tipos antes de usarlos en métodos. NET.</span><span class="sxs-lookup"><span data-stu-id="f9ee4-117">Because **uint** is not a Common Language Specification (CLS)-compliant type, you must assign them to **object** types before using them in .NET methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ee4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9ee4-118">See Also</span></span>  
 <span data-ttu-id="f9ee4-119">[Propiedades del adaptador de MQSeries](../core/mqseries-adapter-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f9ee4-119">[MQSeries Adapter Properties](../core/mqseries-adapter-properties.md) </span></span>  
 <span data-ttu-id="f9ee4-120">[Propiedades relacionadas con BizTalk Server](../core/properties-related-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="f9ee4-120">[Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="f9ee4-121">Propiedades de contexto de MQSeries</span><span class="sxs-lookup"><span data-stu-id="f9ee4-121">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)