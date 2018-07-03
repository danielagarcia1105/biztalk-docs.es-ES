---
title: Generación de confirmación de error error como el límite máximo de X12 transacciones fabricantes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c78a7cef-24ae-4d09-9043-2f53c301302d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9bc40d87e879b1ec6c23d2db0f2dfb466e6f38
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012389"
---
# <a name="error-ack-generation-has-failed-as-maximum-limit-of-x12-transaction-party"></a><span data-ttu-id="c05be-102">Generación de confirmación de error error como el límite máximo de X12 parte de la transacción</span><span class="sxs-lookup"><span data-stu-id="c05be-102">Error-Ack generation has failed as maximum limit of X12 transaction-party</span></span>
## <a name="details"></a><span data-ttu-id="c05be-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c05be-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c05be-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c05be-104">Product Name</span></span>   |                                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                          |
| <span data-ttu-id="c05be-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c05be-105">Product Version</span></span> |                                                                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                      |
|    <span data-ttu-id="c05be-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c05be-106">Event ID</span></span>     |                                                                                                                  -                                                                                                                  |
|  <span data-ttu-id="c05be-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c05be-107">Event Source</span></span>   |                                                                                                         <span data-ttu-id="c05be-108">EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c05be-108">BizTalk Server EDI</span></span>                                                                                                          |
|    <span data-ttu-id="c05be-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c05be-109">Component</span></span>    |                                                                                                             <span data-ttu-id="c05be-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c05be-110">EDI Engine</span></span>                                                                                                              |
|  <span data-ttu-id="c05be-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c05be-111">Symbolic Name</span></span>  |                                                                                                                  -                                                                                                                  |
|  <span data-ttu-id="c05be-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c05be-112">Message Text</span></span>   | <span data-ttu-id="c05be-113">Generación de confirmación; error como el límite máximo del aceptable X12 ha alcanzado el número de control de conjunto de transacciones para entidades {0}.</span><span class="sxs-lookup"><span data-stu-id="c05be-113">Acknowledgement generation has failed as max limit of acceptable X12 transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="c05be-114">Para restablecer el contador, vaya a Entidad, en la pantalla de función de remitente, en el campo ST 2 del administrador de acuerdos de socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="c05be-114">Reset counter by navigating to Party in sender role screen, field ST 2 in Partner Agreement manager.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c05be-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c05be-115">Explanation</span></span>  
 <span data-ttu-id="c05be-116">Este evento de error,  indica que BizTalk Server no pudo generar una confirmación para el intercambio X12 porque el número de control que especificó en el número de control del conjunto de transacciones (ST2) de la confirmación es mayor que el valor máximo permitido para ST2.</span><span class="sxs-lookup"><span data-stu-id="c05be-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the X12 interchange because the control number that it entered in the Transaction set control number (ST2) of the acknowledgment is greater than the maximum value allowed for ST2.</span></span> <span data-ttu-id="c05be-117">En esta instancia, BizTalk Server usó las propiedades de entidad de EDI para crear la confirmación.</span><span class="sxs-lookup"><span data-stu-id="c05be-117">In this instance, BizTalk Server used the EDI party properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="c05be-118">El valor máximo del número de control del conjunto de transacciones depende del número de dígitos usado para el número de control.</span><span class="sxs-lookup"><span data-stu-id="c05be-118">The maximum value of the transaction set control number depends upon the number of digits used for the control number.</span></span> <span data-ttu-id="c05be-119">La longitud máxima de los tres campos es 9; la longitud máxima de los campos prefijo y sufijo es 8.</span><span class="sxs-lookup"><span data-stu-id="c05be-119">The maximum length of all three fields is 9; the maximum length of the prefix and suffix fields is 8.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c05be-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c05be-120">User Action</span></span>  
 <span data-ttu-id="c05be-121">Para resolver este error, restablezca el campo de número de control (ST2.2) del número de referencia del conjunto de transacciones (ST2) en la página Definición de segmentos GS y ST en un valor inferior al límite máximo.</span><span class="sxs-lookup"><span data-stu-id="c05be-121">To resolve this error, reset the control number field (ST2.2) of the Transaction set control number (ST2) in the GS and ST Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="c05be-122">Configure esta propiedad en el cuadro de diálogo Propiedades globales de EDI de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c05be-122">Set this property in the EDI Global Properties dialog box in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>