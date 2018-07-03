---
title: ValidationAdapter | Microsoft Docs
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
ms.openlocfilehash: fbcf26ee8a3a97d2df34bb29dad5d0cf31d4db1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987909"
---
# <a name="validationadapter"></a>ValidationAdapter
El ejemplo ValidationAdapter muestra cómo ejecutar las reglas de validación especiales en un mensaje en un proceso público del Respondedor. Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] realiza la validación en el envío o recepción canalización, de forma nativa y en las orquestaciones. Si desea realizar una validación adicional, puede crear un adaptador de validación. La validación adicional podría incluir la validación de campos cruzados o las reglas de validación específicas de la empresa que no se puede implementar con un XSD.  
  
 Puede crear un adaptador de validación mediante la adición de [!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)] código en el ejemplo ValidationAdapter, las interfaces de publicación y especificar el adaptador en las propiedades del acuerdo. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] a continuación, se llamará a la del adaptador de validación durante el procesamiento del mensaje.  
  
 Puesto que se usa el ValidationAdapter por la orquestación de proceso público, se ejecuta bajo las mismas credenciales que el servicio de host de BizTalk que hospeda esa orquestación.  
  
 El ejemplo ValidationAdapter se encuentra en \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\ ValidationAdapter.  
  
## <a name="demonstrates"></a>Demostraciones  
 El ejemplo ValidationAdapter ilustra la validación de la dirección de correo electrónico en el contenido del servicio. El ejemplo implementa el `IValidateRNIFMessageParts` interfaz. Devuelve un `RNIFException` si la dirección de correo electrónico no está en el formato correcto. Los documentos XML **preambleToValidate**, **serviceHeaderToValidate**, **deliveryHeaderToValidate**, y **serviceContentToValidate**definir la validación.  
  
 El ValidationAdapter, utiliza la propiedad RNIFerror.IsOkToSendException para determinar qué tipo de mensaje que se enviará si se produce un error. Si no se realiza correctamente la validación, el ValidationAdapter RNIFerror.ErrorCode establece en un valor distinto de cero. Si la propiedad RNIFerror.IsOkToSendException es true, el proceso envía una confirmación negativa. Para RNIF 2.0, este es un mensaje de excepción. Para RNIF 1.1, se trata de un mensaje de excepción de confirmación de recepción. Si la propiedad RNIFerror.IsOkToSendException es false y 0A1 está configurado, el proceso enviará un mensaje de 0A1. Una vez que el proceso envía un mensaje de excepción, el mensaje de excepción de confirmación de recepción o el mensaje de 0A1, se cerrará.  
  
 Si la propiedad RNIFerror.IsOkToSendException es false y no está configurado 0A1, el proceso le enviará una excepción ni un 0A1. Registrará el error y, a continuación, en Finalizar.  
  
 Si la validación es correcta, el ValidationAdapter RNIFerror.ErrorCode establece en 0 y BTARN enruta el mensaje al proceso privado. Enruta el mensaje al proceso privado solo si la validación es correcta.  
  
## <a name="to-implement-this-sample"></a>Para implementar este ejemplo  
 Para implementar el ejemplo ValidationAdapter, debe agregar el adaptador de validación al acuerdo.  
  
#### <a name="to-add-the-validation-adapter-to-the-agreement"></a>Para agregar el adaptador de validación del acuerdo  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, señale Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración**.  
  
2. En el [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en **acuerdos**.  
  
3. Haga doble clic en el acuerdo al que desea agregar el adaptador de validación.  
  
4. En el **adaptador de validación** diálogo cuadro, haga clic en el botón de puntos suspensivos (**...** ) situado a la derecha de **nombre del ensamblado**, desplazarse a la ubicación que contiene el ensamblado de adaptador de validación, seleccione el archivo .dll adecuado y, a continuación, haga clic en **abierto**.  
  
5. Haga clic en la flecha hacia abajo para **nombre de la clase**, seleccione la clase de adaptador de validación y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)