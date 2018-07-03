---
title: Fase de validación de XML (procesamiento de intercambio recuperable) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ed00971-d85b-4adb-86c4-c56de7ba7c67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 273a556cd943d5404a4d5dfe38b1f31e29fd752b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012253"
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a><span data-ttu-id="d4d6d-102">Fase de validación de XML (procesamiento de intercambio recuperable)</span><span class="sxs-lookup"><span data-stu-id="d4d6d-102">XML Validation Stage (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="d4d6d-103">El **validador XML** componente de canalización procesa un intercambio en dos modos:</span><span class="sxs-lookup"><span data-stu-id="d4d6d-103">The **XML validator** pipeline component processes an interchange in two modes:</span></span>  
  
-   <span data-ttu-id="d4d6d-104">**Modo estándar**.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-104">**Standard mode**.</span></span> <span data-ttu-id="d4d6d-105">Cuando el **validador XML** componente está configurado para realizar una validación estándar, se validan los mensajes contenidos en un intercambio en una unidad transaccional de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-105">When the **XML validator** component is configured to perform standard validation, the messages contained in an interchange are validated in a transactional unit of work.</span></span> <span data-ttu-id="d4d6d-106">Específicamente, si falla la validación de un mensaje del intercambio, todo el intercambio (que contiene todos los mensajes) se coloca en la cola de suspensión.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-106">Specifically, if validation of a message in the interchange fails, the entire interchange (containing all the messages) is placed in the suspended queue.</span></span>  
  
-   <span data-ttu-id="d4d6d-107">**Modo recuperable**.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-107">**Recoverable mode**.</span></span> <span data-ttu-id="d4d6d-108">Cuando el **validador XML** componente está configurado para realizar el procesamiento de intercambio recuperable, si se produce un error de validación de un mensaje, el mensaje se coloca en la cola de suspensión y la **validador de XML** componente continúa validando los mensajes restantes del intercambio.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-108">When the **XML validator** component is configured to perform recoverable interchange processing, if validation of a message fails, the message is placed in the suspended queue and the **XML validator** component continues to validate remaining messages in the interchange.</span></span>  
  
### <a name="to-configure-recoverable-interchange-processing"></a><span data-ttu-id="d4d6d-109">Procedimiento para configurar el procesamiento de intercambio recuperable</span><span class="sxs-lookup"><span data-stu-id="d4d6d-109">To configure recoverable interchange processing</span></span>  
  
1. <span data-ttu-id="d4d6d-110">Abra una canalización de recepción mediante el diseñador de canalizaciones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-110">Open a receive pipeline by using pipeline designer in Visual Studio.</span></span>  
  
2. <span data-ttu-id="d4d6d-111">Arrastre **validador XML** componente desde el **cuadro de herramientas** a la **validar** fase de la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-111">Drag **XML validator** component from the **Toolbox** to the **Validate** stage of the receive pipeline.</span></span>  
  
3. <span data-ttu-id="d4d6d-112">En la ventana Propiedades, establezca el valor de la **procesamiento de intercambio recuperable** propiedad **True** si desea que el **validador XML** componente a los intercambios de proceso en el modo recuperable, o establezca la propiedad en **False** si desea que el componente para procesar los intercambios del modo estándar.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-112">In the Properties window, set the value of the **Recoverable Interchange Processing** property to **True** if you want the **XML validator** component to process interchanges in the recoverable mode, or set the property to **False** if you want the component to process interchanges in the standard mode.</span></span> <span data-ttu-id="d4d6d-113">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-113">The default value of this property is `False`.</span></span>  
  
   <span data-ttu-id="d4d6d-114">El **XMLValidator** clase en el modelo de objetos, que corresponde a la **validador XML** canalización componente, tiene una propiedad pública denominada **RecoverableInterchangeProcessing**que puede usar para obtener o establecer el modo mediante programación.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-114">The **XMLValidator** class in the object model, which corresponds to the **XML validator** pipeline component, has a public property named **RecoverableInterchangeProcessing** that you can use to get/set the mode programmatically.</span></span> <span data-ttu-id="d4d6d-115">Consulte la documentación de [Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx) clase para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-115">See documentation for [Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx) class for more information.</span></span>  
  
   <span data-ttu-id="d4d6d-116">Los mensajes que se han validado correctamente tienen identificada su entidad de envío según la entidad configurada para el puerto de recepción al que llegó el intercambio primario.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-116">Messages that are successfully validated have their sending party identified according to the party configured for the receive port on which the parent interchange arrived.</span></span> <span data-ttu-id="d4d6d-117">Si se genera un error en alguno de los mensajes extraídos del intercambio, se considera que la resolución de entidades ha dado error en todo el intercambio.</span><span class="sxs-lookup"><span data-stu-id="d4d6d-117">If party resolution for any message extracted from the interchange fails, then the party resolution is considered to have failed for the entire interchange.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d6d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4d6d-118">See Also</span></span>  
 [<span data-ttu-id="d4d6d-119">Cómo configurar el componente de canalización de validador XML</span><span class="sxs-lookup"><span data-stu-id="d4d6d-119">How to Configure the XML Validator Pipeline Component</span></span>](../core/how-to-configure-the-xml-validator-pipeline-component.md)