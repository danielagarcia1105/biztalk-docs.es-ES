---
title: TestCrypto | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, TestCrypto utility
- troubleshooting, TestCrypto utility
- TestCrypto utility
ms.assetid: 02768794-64ac-4d99-930c-738bed9626c5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 632ad57a8bb8a32c8f579a07980480dbd3bf0087
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="testcrypto"></a><span data-ttu-id="fb646-102">TestCrypto</span><span class="sxs-lookup"><span data-stu-id="fb646-102">TestCrypto</span></span>
<span data-ttu-id="fb646-103">Utilice la utilidad TestCrypto para solucionar errores de descifrado de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fb646-103">You use the TestCrypto utility to troubleshoot failures in decrypting messages.</span></span> <span data-ttu-id="fb646-104">La utilidad indica si se produce un error en el descifrado.</span><span class="sxs-lookup"><span data-stu-id="fb646-104">The utility indicates whether decryption fails.</span></span> <span data-ttu-id="fb646-105">Si el descifrado se realice correctamente, la utilidad indica lo que es el certificado y muestra el mensaje descifrado.</span><span class="sxs-lookup"><span data-stu-id="fb646-105">If the decryption succeeds, the utility indicates what the certificate is, and displays the decrypted message.</span></span>  
  
 <span data-ttu-id="fb646-106">Ejecute TestCrypto en un archivo que contiene solo la parte cifrada del mensaje, sin encabezados sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="fb646-106">You run TestCrypto on a file that contains only the encrypted part of the message, without unencrypted headers.</span></span> <span data-ttu-id="fb646-107">Extraer el cifrado objeto binario grande (BLOB) desde el mensaje en un archivo de texto mediante el examen de los mensajes entrantes o recuperar el mensaje de `MessageStorageIn`.</span><span class="sxs-lookup"><span data-stu-id="fb646-107">Extract the encrypted binary large object (BLOB) from the message into a text file, either by sniffing the incoming message or by retrieving the message from `MessageStorageIn`.</span></span>  
  
 <span data-ttu-id="fb646-108">Para obtener más información acerca de cómo recuperar un mensaje de `MessageStorageIn`, consulte [ejemplo GetMessages](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md).</span><span class="sxs-lookup"><span data-stu-id="fb646-108">For more information about retrieving a message from `MessageStorageIn`, see [GetMessages Sample](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md).</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="fb646-109">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="fb646-109">Location in SDK</span></span>  
 <span data-ttu-id="fb646-110">\<*unidad*\>\Program BizTalk \<versión\> Acelerador para RosettaNet\SDK</span><span class="sxs-lookup"><span data-stu-id="fb646-110">\<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-testcrypto"></a><span data-ttu-id="fb646-111">Ejecutando TestCrypto</span><span class="sxs-lookup"><span data-stu-id="fb646-111">Running TestCrypto</span></span>  
  
#### <a name="to-run-testcrypto"></a><span data-ttu-id="fb646-112">Para ejecutar TestCrypto</span><span class="sxs-lookup"><span data-stu-id="fb646-112">To run TestCrypto</span></span>  
  
1.  <span data-ttu-id="fb646-113">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **símbolo**.</span><span class="sxs-lookup"><span data-stu-id="fb646-113">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="fb646-114">Mover a \< *unidad*\>\Program BizTalk \<versión\> Acelerador para RosettaNet\SDK.</span><span class="sxs-lookup"><span data-stu-id="fb646-114">Move to \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span>  
  
3.  <span data-ttu-id="fb646-115">En el símbolo del sistema, escriba **TestCrypto.exe \<filename\>**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fb646-115">At the command prompt, type **TestCrypto.exe \<filename\>**, and then press ENTER.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb646-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb646-116">Remarks</span></span>  
 <span data-ttu-id="fb646-117">Descifrado produce errores si el certificado que busca la utilidad no es el certificado necesario y es válido, o si la utilidad no puede encontrar el certificado.</span><span class="sxs-lookup"><span data-stu-id="fb646-117">Decryption fails if the certificate that the utility finds is not the required and valid certificate, or if the utility cannot find the certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb646-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb646-118">See Also</span></span>  
 [<span data-ttu-id="fb646-119">Utilidades</span><span class="sxs-lookup"><span data-stu-id="fb646-119">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)