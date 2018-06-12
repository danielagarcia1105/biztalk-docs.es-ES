---
title: TestCrypto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, TestCrypto utility
- troubleshooting, TestCrypto utility
- TestCrypto utility
ms.assetid: 02768794-64ac-4d99-930c-738bed9626c5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6948d3883797369c98ad51683cbc59536b9d8fd
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855671"
---
# <a name="testcrypto"></a>TestCrypto
Utilice la utilidad TestCrypto para solucionar errores de descifrado de mensajes. La utilidad indica si se produce un error en el descifrado. Si el descifrado se realice correctamente, la utilidad indica lo que es el certificado y muestra el mensaje descifrado.  
  
 Ejecute TestCrypto en un archivo que contiene solo la parte cifrada del mensaje, sin encabezados sin cifrar. Extraer el cifrado objeto binario grande (BLOB) desde el mensaje en un archivo de texto mediante el examen de los mensajes entrantes o recuperar el mensaje de `MessageStorageIn`.  
  
 Para obtener más información acerca de cómo recuperar un mensaje de `MessageStorageIn`, consulte [ejemplo GetMessages](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md).  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK  
  
## <a name="running-testcrypto"></a>Ejecutando TestCrypto  
  
#### <a name="to-run-testcrypto"></a>Para ejecutar TestCrypto  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **símbolo**.  
  
2.  Mover a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK.  
  
3.  En el símbolo del sistema, escriba **TestCrypto.exe \<filename\>**, y, a continuación, presione ENTRAR.  
  
## <a name="remarks"></a>Notas  
 Descifrado produce errores si el certificado que busca la utilidad no es el certificado necesario y es válido, o si la utilidad no puede encontrar el certificado.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
