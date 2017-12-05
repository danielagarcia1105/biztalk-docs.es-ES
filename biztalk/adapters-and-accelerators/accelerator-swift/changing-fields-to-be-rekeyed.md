---
title: "Cambiar los campos regeneración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- rekeyed fields
- Message Repair and New Submission, modifying fields
- Message Repair and New Submission, rekeyed fields
ms.assetid: aaf353f7-0e43-403e-b72a-88e5dd07f4ac
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04693bf4c4d441487a3ce38f886bc680b1db368b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="changing-fields-to-be-rekeyed"></a><span data-ttu-id="4bdf9-102">Cambiar los campos de regeneración</span><span class="sxs-lookup"><span data-stu-id="4bdf9-102">Changing Fields to Be Rekeyed</span></span>
<span data-ttu-id="4bdf9-103">En el paso de comprobación de un flujo de trabajo de reparación de mensaje [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] quita los datos de un número de campos para que el Verificador debe volver a escribir o regenerar, esos datos.</span><span class="sxs-lookup"><span data-stu-id="4bdf9-103">In the verification step of a message repair workflow, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] removes the data from a number of fields so that the verifier must re-enter, or rekey, that data.</span></span> <span data-ttu-id="4bdf9-104">Puede personalizar qué campos de la RekeyVerify [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario necesita regeneración.</span><span class="sxs-lookup"><span data-stu-id="4bdf9-104">You can customize which fields in the RekeyVerify [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form need to be rekeyed.</span></span> <span data-ttu-id="4bdf9-105">Puede hacerlo en el archivo MrsrXpathConfig.xml, que se encuentra en la \< *unidad*\>: \Program Acelerador de BizTalk para la carpeta SWIFT\MRSR.</span><span class="sxs-lookup"><span data-stu-id="4bdf9-105">You do so in the MrsrXpathConfig.xml file, which is located in the \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\MRSR folder.</span></span>  
  
 <span data-ttu-id="4bdf9-106">El archivo MrsrXpathConfig.xml contiene una serie de nodos para el tipo de mensaje procesado.</span><span class="sxs-lookup"><span data-stu-id="4bdf9-106">The MrsrXpathConfig.xml file contains a series of nodes for the message type processed.</span></span> <span data-ttu-id="4bdf9-107">Cada nodo de tipo de mensaje contiene una serie de nodos de campo, uno para cada campo.</span><span class="sxs-lookup"><span data-stu-id="4bdf9-107">Each message-type node contains a series of field nodes, one for each field.</span></span> <span data-ttu-id="4bdf9-108">Puede cambiar los campos regeneración abriendo MrsrXpathConfig.xml en un editor de texto, como el Bloc de notas y agregando o quitando un \<ruta de acceso\> nodo para el campo.</span><span class="sxs-lookup"><span data-stu-id="4bdf9-108">You can change the fields to be rekeyed by opening MrsrXpathConfig.xml in a text editor, such as Notepad, and adding or removing a \<path\> node for the field.</span></span>  
  
 <span data-ttu-id="4bdf9-109">El \<ruta de acceso\> nodo contiene las rutas de acceso para el tipo de mensaje y el campo.</span><span class="sxs-lookup"><span data-stu-id="4bdf9-109">The \<path\> node contains paths for the message type and the field.</span></span> <span data-ttu-id="4bdf9-110">Por ejemplo, la entrada de la ruta de acceso de destino en el bloque de encabezado de la aplicación de entrada de un mensaje de MT103 es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bdf9-110">For example, the entry for the Destination Path in the Input Application Header Block of an MT103 message is the following:</span></span>  
  
```  
<path>/*[local-name()='SWIFT_CATEGORY1_MT103_Interchange' and namespace-uri()'http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category1/MT103']/*[local-name()='SWIFTHeader' and namespace-uri=']'']/*[local-name()='ApplicationHeaderBlock_Input' and namespace-uri90='']/*[local-name()='DestinationAddress' and namespace-uri()='']</path>  
```  
  
 <span data-ttu-id="4bdf9-111">Es más fácil agregar un nuevo campo regeneración mediante copiar y pegar, a continuación, una entrada existente y, a continuación, cambiar las rutas de acceso relevantes.</span><span class="sxs-lookup"><span data-stu-id="4bdf9-111">It is easiest to add a new field to be rekeyed by copying and then pasting an existing entry, and then changing the relevant paths.</span></span> <span data-ttu-id="4bdf9-112">Por ejemplo, para forzar la regeneración de claves del campo de fecha en la sección de 32 a fecha moneda bancos vinculados liquidar importe del valor de un mensaje MT103, realice las sustituciones de tres siguientes en el código anterior.</span><span class="sxs-lookup"><span data-stu-id="4bdf9-112">For example, to force rekey of the Date field in the Value Date Currency Interbank Settled Amount 32A section of an MT103 message, make the following three replacements to the preceding code.</span></span> <span data-ttu-id="4bdf9-113">El resto del código sigue siendo el mismo.</span><span class="sxs-lookup"><span data-stu-id="4bdf9-113">The rest of the code remains the same.</span></span>  
  
|<span data-ttu-id="4bdf9-114">Reemplace este</span><span class="sxs-lookup"><span data-stu-id="4bdf9-114">Replace this</span></span>|<span data-ttu-id="4bdf9-115">Con esto</span><span class="sxs-lookup"><span data-stu-id="4bdf9-115">With this</span></span>|  
|------------------|---------------|  
|`SWIFTHeader`|`SWIFT_CATEGORY1_MT103`|  
|`ApplicationHeaderBlock_Input`|`ValueDateCurrencyInterbankSettledAmount_32A`|  
|`DestinationAddress`|`Date`|  
  
 <span data-ttu-id="4bdf9-116">Para obtener más información acerca de campos de regeneración de claves, consulte [un procesamiento especial en la reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md).</span><span class="sxs-lookup"><span data-stu-id="4bdf9-116">For more information about rekeying fields, see [Special Processing in Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md).</span></span>