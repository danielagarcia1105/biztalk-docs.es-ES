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
# <a name="changing-fields-to-be-rekeyed"></a>Cambiar los campos de regeneración
En el paso de comprobación de un flujo de trabajo de reparación de mensaje [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] quita los datos de un número de campos para que el Verificador debe volver a escribir o regenerar, esos datos. Puede personalizar qué campos de la RekeyVerify [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario necesita regeneración. Puede hacerlo en el archivo MrsrXpathConfig.xml, que se encuentra en la \< *unidad*\>: \Program Acelerador de BizTalk para la carpeta SWIFT\MRSR.  
  
 El archivo MrsrXpathConfig.xml contiene una serie de nodos para el tipo de mensaje procesado. Cada nodo de tipo de mensaje contiene una serie de nodos de campo, uno para cada campo. Puede cambiar los campos regeneración abriendo MrsrXpathConfig.xml en un editor de texto, como el Bloc de notas y agregando o quitando un \<ruta de acceso\> nodo para el campo.  
  
 El \<ruta de acceso\> nodo contiene las rutas de acceso para el tipo de mensaje y el campo. Por ejemplo, la entrada de la ruta de acceso de destino en el bloque de encabezado de la aplicación de entrada de un mensaje de MT103 es la siguiente:  
  
```  
<path>/*[local-name()='SWIFT_CATEGORY1_MT103_Interchange' and namespace-uri()'http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category1/MT103']/*[local-name()='SWIFTHeader' and namespace-uri=']'']/*[local-name()='ApplicationHeaderBlock_Input' and namespace-uri90='']/*[local-name()='DestinationAddress' and namespace-uri()='']</path>  
```  
  
 Es más fácil agregar un nuevo campo regeneración mediante copiar y pegar, a continuación, una entrada existente y, a continuación, cambiar las rutas de acceso relevantes. Por ejemplo, para forzar la regeneración de claves del campo de fecha en la sección de 32 a fecha moneda bancos vinculados liquidar importe del valor de un mensaje MT103, realice las sustituciones de tres siguientes en el código anterior. El resto del código sigue siendo el mismo.  
  
|Reemplace este|Con esto|  
|------------------|---------------|  
|`SWIFTHeader`|`SWIFT_CATEGORY1_MT103`|  
|`ApplicationHeaderBlock_Input`|`ValueDateCurrencyInterbankSettledAmount_32A`|  
|`DestinationAddress`|`Date`|  
  
 Para obtener más información acerca de campos de regeneración de claves, consulte [un procesamiento especial en la reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md).