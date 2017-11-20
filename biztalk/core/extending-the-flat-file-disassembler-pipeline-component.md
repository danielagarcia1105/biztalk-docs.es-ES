---
title: "Extender el componente de canalización de desensamblador de archivos sin formato | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, code sample
- pipeline components [custom], flat file documents
- pipeline components [custom], disassembling
ms.assetid: 4bcc746a-696a-4e5c-be01-f8409fce21fa
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 031189c0ecadfd8a7baff38200f044598e800437
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="extending-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="03dda-102">Extender el componente de canalización de desensamblador de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="03dda-102">Extending the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="03dda-103">El siguiente ejemplo ilustra cómo crear un desensamblador personalizado para analizar documentos de archivos sin formato codificados con UTF-7.</span><span class="sxs-lookup"><span data-stu-id="03dda-103">The following sample illustrates how to create a custom disassembler to parse flat file documents that are UTF-7 encoded.</span></span> <span data-ttu-id="03dda-104">Para procesar documentos UTF-7, el componente hereda de la **FFDasmComp** clase y, a continuación, reemplaza su **GetDataReader** método.</span><span class="sxs-lookup"><span data-stu-id="03dda-104">To process UTF-7 documents, the component inherits from the **FFDasmComp** class and then overrides its **GetDataReader** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03dda-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03dda-105">Example</span></span>  
  
```  
using System;  
using System.Text;  
using System.IO;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.ParsingEngine;  
using Microsoft.BizTalk.Component;  
using System.Runtime.InteropServices;  
  
namespace Microsoft.BizTalk.Test  
{  
   /// <summary>  
   /// Implements FF disassembler which always uses UTF-7 encoding.  
   /// </summary>  
   [ComponentCategory(CategoryTypes.CATID_PipelineComponent)]  
   [ComponentCategory(CategoryTypes.CATID_DisassemblingParser)]  
   [ComponentCategory(CategoryTypes.CATID_Streamer)]  
   [Guid("A6E5F54F-7902-4e1a-84D8-5C7584F0ECF2")]  
   public class Utf7FFDasm :   
      FFDasmComp,  
      IBaseComponent  
   {  
      /// <summary>  
      /// Initializes a Utf7FFAsmDasm instance.  
      /// </summary>  
      public Utf7FFDasm()  
      {  
      }  
  
      /// <summary>  
      /// Name property  
      /// </summary>  
      public new string Name   
      {  
         get   
         {  
            return "UTF-7 FlatFile Disassembler";  
         }  
      }  
  
      /// <summary>  
      /// Version property  
      /// </summary>  
      public new string Version   
      {  
         get   
         {  
            return "1.0";  
         }  
      }  
  
      /// <summary>  
      /// Description property  
      /// </summary>  
      public new string Description   
      {  
         get   
         {  
            return "UTF-7 FlatFile Disassembler";  
         }  
      }  
  
      /// <summary>  
      /// Gets a data reader instance  
      /// </summary>  
      /// <param name="dataStream">Data stream</param>  
      /// <param name="dataEncoding">Data encoding</param>  
      /// <param name="detectEncodingFromByteOrderMarks">Detect encoding from a byte order mark</param>  
      /// <returns>IDataReader instance</returns>  
      protected override IDataReader GetDataReader(Stream dataStream, Encoding dataEncoding, bool detectEncodingFromByteOrderMarks)  
      {  
         // Delegate call to the base implementation passing fixed UTF-7 encoding  
            return base.GetDataReader(dataStream, Encoding.UTF7, false);  
      }  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="03dda-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03dda-106">Example</span></span>  
 <span data-ttu-id="03dda-107">El siguiente ejemplo ilustra cómo crear un desensamblador personalizado para el procesamiento transaccional de intercambios de archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="03dda-107">The following example illustrates how to create a custom disassembler for transactional processing of flat file interchanges.</span></span> <span data-ttu-id="03dda-108">Difiere del Desensamblador de archivos sin formato estándar en que no genera ningún documento desensamblado hasta que no se procesa por completo todo el intercambio de entrada.</span><span class="sxs-lookup"><span data-stu-id="03dda-108">It differs from the standard Flat File Disassembler in that it does not produce any disassembled documents until the entire input interchange is completely processed.</span></span> <span data-ttu-id="03dda-109">Esta implementación de componentes hereda de la **FFDasmComp** clase e invalida el **GetNext** método.</span><span class="sxs-lookup"><span data-stu-id="03dda-109">This component implementation inherits from the **FFDasmComp** class and overrides the **GetNext** method.</span></span> <span data-ttu-id="03dda-110">En la primera llamada a la **GetNext** método, procesa todos los mensajes del intercambio, se almacena en un **ArrayList**y devuelve el primer mensaje de la **ArrayList**.</span><span class="sxs-lookup"><span data-stu-id="03dda-110">On the first call to the **GetNext** method, it processes all messages in the interchange, stores them in an **ArrayList**, and returns the first message from the **ArrayList**.</span></span> <span data-ttu-id="03dda-111">En las llamadas posteriores, se devuelve el siguiente mensaje de la **ArrayList**.</span><span class="sxs-lookup"><span data-stu-id="03dda-111">On subsequent calls, it returns the next message from the **ArrayList**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03dda-112">La implementación del método GetNext() en el ejemplo de código siguiente no resultaría adecuada para el procesamiento de documentos grandes, ya que conserva el intercambio completo en memoria.</span><span class="sxs-lookup"><span data-stu-id="03dda-112">The implementation of the GetNext() method in the code sample below would not be suitable for the processing of large documents because it retains the entire interchange in memory.</span></span>  <span data-ttu-id="03dda-113">Si utiliza esta técnica para documentos grandes, podrían agotarse los recursos de memoria y provocar una disminución del rendimiento o un comportamiento inestable.</span><span class="sxs-lookup"><span data-stu-id="03dda-113">Using this technique for large documents could exhaust memory resources and cause degraded performance or unstable behavior.</span></span>  
  
```  
using System;  
using System.Collections;  
using System.Runtime.InteropServices;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.Component;  
  
namespace Microsoft.BizTalk.Component  
{  
   /// <summary>  
   /// Summary description for Class1.  
   /// </summary>  
   [ComponentCategory(CategoryTypes.CATID_PipelineComponent)]  
   [ComponentCategory(CategoryTypes.CATID_DisassemblingParser)]  
   [Guid("EB4714A8-FD97-43de-84E2-E011648F349B")]  
   public class TransactionalFFDasm :   
      FFDasmComp,  
      IBaseComponent,  
      IDisassemblerComponent  
   {  
      public TransactionalFFDasm()  
      {  
      }  
  
      #region IBaseComponent Members  
  
      public new string Description  
      {  
         get  
         {  
            return "Transactional Flat File Disassembler";  
         }  
      }  
  
      public new string Name  
      {  
         get  
         {  
            return "Transactional Flat File Disassembler";  
         }  
      }  
  
      public new string Version  
      {  
         get  
         {  
            return "1.0";  
         }  
      }  
  
      #endregion  
  
      #region IDisassemblerComponent Members  
  
      public new void Disassemble(IPipelineContext pContext, IBaseMessage pInMsg)  
      {  
         base.Disassemble(pContext, pInMsg);  
      }  
  
      public new IBaseMessage GetNext(IPipelineContext pContext)  
      {  
         // Check if don't need to stop collecting messages  
         if (currentMessage == 0)  
         {  
            messageInterchange = new ArrayList();  
            currentMessage = 0;  
  
            // Collect messages from the standard disassembler  
            IBaseMessage disassembledMessage = null;  
            while ((disassembledMessage = base.GetNext(pContext)) != null)  
            {  
               byte[] buffer = new byte[4096];  
               int count = 0;  
  
               // Create a new memory stream to contain the disassembled message.  
               MemoryStream messageStream = new MemoryStream();  
  
               // Get a stream pointer to the disassembled stream.  
               Stream disassembledStream = disassembledMessage.BodyPart.GetOriginalDataStream();  
  
               // Write the disassembled message to the memory stream  
               while (0 != (count == disassembledStream.Read(buffer, 0, 4096)))  
               {  
                  messageStream.Write(buffer, 0, count);  
               } // end-while  
  
               // Rewind the stream to the beginning  
               messageStream.Seek(0, SeekOrigin.Begin);  
  
               // Replace the stream on the disassembled message with the memory stream.  
               disassembledMessage.BodyPart.data = messageStream;  
  
               // Add this message to the ArrayList of messages.  
               messageInterchange.Add(disassembledMessage);  
            } // end-while  
  
            // Check if no messages were collected, just return nothing  
            if (0 == messageInterchange.Count)  
               return null;  
         } // end-if  
  
         // Check if all collected messages are returned  
         if (currentMessage == messageInterchange.Count)  
            return null;  
  
         // Return the current collected message  
         return (IBaseMessage)messageInterchange[currentMessage++];  
      } // end-method GetNext()  
  
      #endregion  
  
      private ArrayList messageInterchange = null;  
      private int currentMessage = 0;  
   }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="03dda-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="03dda-114">See Also</span></span>  
 [<span data-ttu-id="03dda-115">Desarrollar un componente de canalización de desensamblado</span><span class="sxs-lookup"><span data-stu-id="03dda-115">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)