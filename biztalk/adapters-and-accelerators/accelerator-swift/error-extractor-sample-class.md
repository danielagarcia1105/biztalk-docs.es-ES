---
title: Clase de ejemplo de Extractor de error | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Error Extractor Sample class
- errors, Error Extractor Sample class
ms.assetid: d0d59b21-d80a-4466-a77a-1d3b7df1bc2a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1085af05221b252bb6942e2c32bbe1f91c8d7688
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010773"
---
# <a name="error-extractor-sample-class"></a><span data-ttu-id="43969-102">Clase de ejemplo de Extractor de error</span><span class="sxs-lookup"><span data-stu-id="43969-102">Error Extractor Sample Class</span></span>
<span data-ttu-id="43969-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] Desensamblador errores a un objeto XML se serializa y se adjunta el objeto XML a la sección de errores de un mensaje de varias partes.</span><span class="sxs-lookup"><span data-stu-id="43969-103">The Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] disassembler serializes errors to an XML object, and attaches the XML object to the error section of a multipart message.</span></span> <span data-ttu-id="43969-104">El desensamblador, a continuación, publica el mensaje con errores en la base de datos de cuadro de mensajes tal como lo haría con un mensaje válido.</span><span class="sxs-lookup"><span data-stu-id="43969-104">The disassembler then publishes the failed message to the MessageBox database just as it would a valid message.</span></span> <span data-ttu-id="43969-105">Por lo tanto, no se pudo detalles del error de transporte de mensajes en la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="43969-105">Therefore, failed messages carry error details into the MessageBox database.</span></span> <span data-ttu-id="43969-106">Puede usar la clase de ejemplo de Extractor de Error para extraer los detalles del error de un mensaje con errores y generar un archivo que tiene los detalles del error y otro que tiene el mensaje original.</span><span class="sxs-lookup"><span data-stu-id="43969-106">You can use the Error Extractor Sample Class to extract the error details from a failed message, and generate one file that has the error details and another file that has the original message.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="43969-107">La clase de ejemplo de Extractor de Error es el código de ejemplo en el SDK.</span><span class="sxs-lookup"><span data-stu-id="43969-107">The Error Extractor Sample Class is sample code in the SDK.</span></span> <span data-ttu-id="43969-108">No está pensado para su uso en producción.</span><span class="sxs-lookup"><span data-stu-id="43969-108">It is not intended for use in production.</span></span>  
  
 <span data-ttu-id="43969-109">Para usar la clase de ejemplo de Extractor de Error, debe crear una orquestación para procesar el mensaje con errores.</span><span class="sxs-lookup"><span data-stu-id="43969-109">To use the Error Extractor Sample Class, you must create an orchestration to process the failed message.</span></span> <span data-ttu-id="43969-110">Esta orquestación incluye pasos para extraer el cuerpo del mensaje con errores, extraer la parte de error del mensaje con errores y, a continuación, escribir el cuerpo y el elemento de error en los archivos XML independientes.</span><span class="sxs-lookup"><span data-stu-id="43969-110">This orchestration includes steps to extract the body of the failed message, extract the error part of the failed message, and then write the body and the error part to separate XML files.</span></span> <span data-ttu-id="43969-111">La orquestación representa cada uno de estos pasos en una fase de la expresión que se llama a uno o varios de los siguientes métodos de la clase de ejemplo de Extractor de Error:</span><span class="sxs-lookup"><span data-stu-id="43969-111">The orchestration represents each of these steps in an expression stage that calls one or more of the following methods in the Error Extractor Sample Class:</span></span>  
  
## <a name="getbodypartasstring-method"></a><span data-ttu-id="43969-112">Método GetBodyPartAsString</span><span class="sxs-lookup"><span data-stu-id="43969-112">GetBodyPartAsString method</span></span>  
 <span data-ttu-id="43969-113">Este método devuelve una cadena que contiene el XML que se encuentra en la parte del cuerpo del mensaje XLANG 'xm'.</span><span class="sxs-lookup"><span data-stu-id="43969-113">This method returns a string that contains the XML found in the body part of the XLANG message 'xm'.</span></span> <span data-ttu-id="43969-114">El método espera el mensaje XLANG 'xm' para que contenga una parte del cuerpo denominada "BodySegment".</span><span class="sxs-lookup"><span data-stu-id="43969-114">The method expects the XLANG message 'xm' to contain a body part called "BodySegment."</span></span> <span data-ttu-id="43969-115">Por lo tanto, debe declarar 'xm' en la orquestación de llamada con este nombre de parte del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="43969-115">Therefore, you must declare 'xm' in the calling orchestration with this body part name.</span></span> <span data-ttu-id="43969-116">Si no existe como parte de "xm", "BodySegment" **GetBodyPartAsString** produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="43969-116">If "BodySegment" does not exist as a part of 'xm', **GetBodyPartAsString** throws an exception.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a><span data-ttu-id="43969-117">Método GetErrorPartAsString</span><span class="sxs-lookup"><span data-stu-id="43969-117">GetErrorPartAsString method</span></span>  
 <span data-ttu-id="43969-118">Este método devuelve una cadena que contiene el XML se encuentra en la parte de error del mensaje XLANG 'xm'.</span><span class="sxs-lookup"><span data-stu-id="43969-118">This method returns a string that contains the XML found in the error part of the XLANG message 'xm'.</span></span> <span data-ttu-id="43969-119">El método espera el mensaje XLANG 'xm' para que contenga una parte de error denominado "ErrorSegment."</span><span class="sxs-lookup"><span data-stu-id="43969-119">The method expects the XLANG message 'xm' to contain an error part called "ErrorSegment."</span></span> <span data-ttu-id="43969-120">Por lo tanto, debe declarar 'xm' en la orquestación de llamada con este nombre de parte del error.</span><span class="sxs-lookup"><span data-stu-id="43969-120">Therefore, you must declare 'xm' in the calling orchestration with this error part name.</span></span> <span data-ttu-id="43969-121">Si no existe como parte de "xm", "ErrorSegment" **GetErrorPartAsString** produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="43969-121">If "ErrorSegment" does not exist as a part of 'xm', **GetErrorPartAsString** throws an exception.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a><span data-ttu-id="43969-122">Método WriteToFile</span><span class="sxs-lookup"><span data-stu-id="43969-122">WriteToFile method</span></span>  
 <span data-ttu-id="43969-123">Este método escribe la cadena desde el *mensaje* parámetro en el archivo especificado por el *filePath* parámetro.</span><span class="sxs-lookup"><span data-stu-id="43969-123">This method writes the string from the *message* parameter to the file specified by the *filePath* parameter.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 <span data-ttu-id="43969-124">El programa de instalación de A4SWIFT la clase de ejemplo de Extractor de Error (SWIFTErrorExtractor.dll) se instala como parte del SDK de A4SWIFT en \< *unidad*\>: Acelerador de BizTalk para SWIFT\SDK\Tutorial\ \Program Files\Microsoft SWIFTErrorExtractor.</span><span class="sxs-lookup"><span data-stu-id="43969-124">A4SWIFT Setup installs the Error Extractor Sample Class (SWIFTErrorExtractor.dll) as part of the A4SWIFT SDK in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor.</span></span> <span data-ttu-id="43969-125">Esta carpeta también incluye el código fuente de la clase de ejemplo (ErrorExtractor.cs).</span><span class="sxs-lookup"><span data-stu-id="43969-125">This folder also includes the source code for the sample class (ErrorExtractor.cs).</span></span>  
  
 <span data-ttu-id="43969-126">Para llamar a SWIFTErrorExtractor.dll desde la orquestación, debe publicar el archivo .dll en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="43969-126">To call SWIFTErrorExtractor.dll from the orchestration, you must publish the .dll file to the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43969-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="43969-127">See Also</span></span>  
 [<span data-ttu-id="43969-128">Herramientas</span><span class="sxs-lookup"><span data-stu-id="43969-128">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)