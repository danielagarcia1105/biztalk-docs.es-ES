---
title: ValidationAdapter | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fe99350-14c0-4ddb-b257-af9a0c4258f6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a325a561017c6efaf6d6aefe2e271c834c13a363
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966442"
---
# <a name="validationadapter"></a>ValidationAdapter
El ejemplo ValidationAdapter muestra cómo ejecutar las reglas de validación especiales en un mensaje en un proceso público de servicio de respuesta. [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] realiza la validación en el envío o recepción canalización, de forma nativa y en orquestaciones. Si desea realizar una validación adicional, puede crear un adaptador de validación. La validación adicional podría incluir la validación de campos cruzados o las reglas de validación específicos del negocio que no se implementan mediante un XSD.  
  
 Puede crear un adaptador de validación mediante la adición de [!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)] código en el ejemplo de ValidationAdapter, las interfaces de publicación y especificando el adaptador en las propiedades del acuerdo. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]a continuación, se llamará a la del adaptador de validación durante el procesamiento del mensaje.  
  
 Puesto que se usa el ValidationAdapter por la orquestación de proceso público, se ejecuta bajo las mismas credenciales que el servicio de host de BizTalk que hospeda dicha orquestación.  
  
 El ejemplo ValidationAdapter se encuentra en \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Acelerador para RosettaNet\SDK\ ValidationAdapter.  
  
## <a name="demonstrates"></a>Demostraciones  
 El ejemplo ValidationAdapter ilustra la validación de la dirección de correo electrónico en el contenido del servicio. El ejemplo implementa el `IValidateRNIFMessageParts` interfaz. Devuelve un `RNIFException` si la dirección de correo electrónico no está en el formato correcto. Los documentos XML **preambleToValidate**, **serviceHeaderToValidate**, **deliveryHeaderToValidate**, y **serviceContentToValidate**definir la validación.  
  
 El ValidationAdapter usa la propiedad RNIFerror.IsOkToSendException para determinar qué tipo de mensaje que se envía cuando se produce un error. Si la validación no se completa correctamente, el ValidationAdapter establece RNIFerror.ErrorCode en un valor distinto de cero. Si la propiedad RNIFerror.IsOkToSendException es true, el proceso envía una confirmación negativa. Para RNIF 2.0, se trata de un mensaje de excepción. Para RNIF 1.1, se trata de un mensaje de excepción de confirmación de recepción. Si la propiedad RNIFerror.IsOkToSendException es false y 0A1 está configurado, el proceso enviará un mensaje 0A1. Una vez que el proceso envía un mensaje de excepción, el mensaje de excepción de confirmación de recepción o el mensaje de 0A1, se cerrará.  
  
 Si la propiedad RNIFerror.IsOkToSendException es false y 0A1 no está configurado, el proceso enviará una excepción ni un 0A1. Registrará el error y, a continuación, finalice.  
  
 Si la validación es correcta, el ValidationAdapter establece RNIFerror.ErrorCode en 0 y BTARN enruta el mensaje al proceso privado. Enruta el mensaje al proceso privado solo si la validación es correcta.  
  
## <a name="to-implement-this-sample"></a>Para implementar este ejemplo  
 Para implementar el ejemplo ValidationAdapter, debe agregar el adaptador de validación para el acuerdo.  
  
#### <a name="to-add-the-validation-adapter-to-the-agreement"></a>Para agregar el adaptador de validación para el acuerdo  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración**.  
  
2.  En el [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en **contratos**.  
  
3.  Haga doble clic en el acuerdo al que desea agregar el adaptador de validación.  
  
4.  En el **validación adaptador** diálogo cuadro, haga clic en el botón de puntos suspensivos (**...** ) situado a la derecha de **nombre de ensamblado**, desplácese a la ubicación que contiene el ensamblado de adaptador de validación, seleccione el archivo .dll adecuado y, a continuación, haga clic en **abiertos**.  
  
5.  Haga clic en la flecha hacia abajo para **nombre de la clase**, seleccione la clase de adaptador de validación y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)