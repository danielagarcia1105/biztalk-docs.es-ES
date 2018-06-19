---
title: Transformación de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, data translation
- data translation, about data translation
- data transformation, about data transformation
- maps, data transformation
- data transformation, maps
- data translation, maps
ms.assetid: a6aa5e9a-8d9c-478d-8f69-f9b16ed1a18c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ee1cd9b7e825f210032f7caaaa292496cfa44c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238652"
---
# <a name="data-transformation"></a><span data-ttu-id="a20a4-102">Transformación de datos</span><span class="sxs-lookup"><span data-stu-id="a20a4-102">Data Transformation</span></span>
<span data-ttu-id="a20a4-103">Asignar datos se fundamenta en la transformación de datos.</span><span class="sxs-lookup"><span data-stu-id="a20a4-103">Mapping data relies on data transformation.</span></span>  
  
 <span data-ttu-id="a20a4-104">La transformación de datos es el proceso de creación de una correspondencia entre registros y campos de un esquema de origen y registros y campos (a menudo diferentes) en un esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="a20a4-104">Data transformation is the process of creating a correspondence between records and fields of a source schema to (often different) records and fields in a destination schema.</span></span> <span data-ttu-id="a20a4-105">Un ejemplo de transformación de datos es asignar la información de direcciones de envío y facturación de un pedido a una factura.</span><span class="sxs-lookup"><span data-stu-id="a20a4-105">An example of data transformation is to map shipping and billing address information from a purchase order to an invoice.</span></span> <span data-ttu-id="a20a4-106">Éste es el tipo de asignación más básico.</span><span class="sxs-lookup"><span data-stu-id="a20a4-106">This is the most basic type of mapping.</span></span> <span data-ttu-id="a20a4-107">La transformación de datos también puede aplicarse a operaciones como:</span><span class="sxs-lookup"><span data-stu-id="a20a4-107">Data transformation can also apply to operations such as:</span></span>  
  
-   <span data-ttu-id="a20a4-108">Calcular el promedio de datos desde un registro de bucle y enviar el resultado a un solo campo del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="a20a4-108">Averaging data from a looping record and sending the output to a single field in the destination schema.</span></span>  
  
-   <span data-ttu-id="a20a4-109">Convertir datos de caracteres en su formato equivalente ASCII.</span><span class="sxs-lookup"><span data-stu-id="a20a4-109">Converting character data to its ASCII format.</span></span>  
  
-   <span data-ttu-id="a20a4-110">Sumar o restar datos de uno o más registros y colocar el resultado en un solo campo del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="a20a4-110">Adding or subtracting data from one or more records and putting the result in a single field in the destination schema.</span></span>  
  
 <span data-ttu-id="a20a4-111">Si desea traducir datos de un formato a otro, debería usar una canalización.</span><span class="sxs-lookup"><span data-stu-id="a20a4-111">If you want to translate data from one format to another, you would use a pipeline.</span></span> <span data-ttu-id="a20a4-112">Esto puede ser útil para resolver problemas de integración de aplicaciones de negocio, porque traduce un tipo de mensaje dado en formatos alternativos que los sistemas existentes requieren, pero no puede hacerse mediante una asignación.</span><span class="sxs-lookup"><span data-stu-id="a20a4-112">This can be helpful in solving enterprise application integration problems by translating a given type of message into alternative formats required by existing systems but cannot be done using a map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a20a4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a20a4-113">See Also</span></span>  
 <span data-ttu-id="a20a4-114">[Mapas](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="a20a4-114">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="a20a4-115">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a20a4-115">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)