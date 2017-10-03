---
title: "Las referencias en el código de usuario de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a1584be-35fd-4dc2-a5a9-559300e67e0e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 264f50da516f44d8fc87186614a79bb81aaf77ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-references-in-user-code"></a><span data-ttu-id="b1e93-102">Referencias de mensajes en código de usuario</span><span class="sxs-lookup"><span data-stu-id="b1e93-102">Message References in User Code</span></span>
<span data-ttu-id="b1e93-103">Cuando se construye un mensaje, una representación de éste se encuentra en la base de datos de cuadro de mensajes y otra en la memoria del equipo.</span><span class="sxs-lookup"><span data-stu-id="b1e93-103">When a message is constructed, a representation of the message is in the MessageBox database and another representation is in memory on the computer.</span></span> <span data-ttu-id="b1e93-104">Si se realiza la asignación del mensaje pasando una referencia del mensaje a un objeto .NET o a un ensamblado externo y, a continuación, uno de ellos modifica la representación que se encuentra en la memoria del equipo, el motor de orquestaciones de BizTalk no tendrá constancia de la modificación.</span><span class="sxs-lookup"><span data-stu-id="b1e93-104">If you make the message assignment by passing a message reference to a .NET object or to an external assembly, and then the .NET object or the external assembly modifies the representation in memory on the computer, the BizTalk Orchestration Engine is not aware of the modification.</span></span>  
  
 <span data-ttu-id="b1e93-105">Además, el motor de orquestaciones no invalida los datos de partes del mensaje que se encuentran en la representación de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b1e93-105">Moreover, the orchestration engine does not invalidate the message part data that is in the representation in the MessageBox database.</span></span> <span data-ttu-id="b1e93-106">Estos datos cuentan con los siguientes modos de representación:</span><span class="sxs-lookup"><span data-stu-id="b1e93-106">Message part data has the following modes of representation:</span></span>  
  
-   <span data-ttu-id="b1e93-107">Representación XmlDocument</span><span class="sxs-lookup"><span data-stu-id="b1e93-107">XmlDocument representation</span></span>  
  
-   <span data-ttu-id="b1e93-108">Representación de objetos</span><span class="sxs-lookup"><span data-stu-id="b1e93-108">Object representation</span></span>  
  
-   <span data-ttu-id="b1e93-109">Representación de secuencias</span><span class="sxs-lookup"><span data-stu-id="b1e93-109">Stream representation</span></span>  
  
-   <span data-ttu-id="b1e93-110">Representación UnderlyingPart</span><span class="sxs-lookup"><span data-stu-id="b1e93-110">UnderlyingPart representation</span></span>  
  
 <span data-ttu-id="b1e93-111">El modo en que los datos de partes del mensaje se representen en la memoria dependerá de la construcción del mensaje y de si el tipo es una clase .NET o un esquema en lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="b1e93-111">How the message part data is represented in memory depends on the message construction and whether the type is a .NET class or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="b1e93-112">Sin embargo, la representación UnderlyingPart siempre es una secuencia que apunta a la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b1e93-112">However, the UnderlyingPart representation is always a stream pointing into the MessageBox database.</span></span> <span data-ttu-id="b1e93-113">Puesto que los mensajes en BizTalk Server son inmutables una vez confirmado el mensaje en la base de datos de cuadro de mensajes, el motor de orquestaciones utiliza la representación de esta base de datos para hacer referencia a los datos de partes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b1e93-113">Because messages in BizTalk Server are immutable after the message is committed to the MessageBox database, the orchestration engine uses the representation in the MessageBox database to reference message part data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1e93-114">Un mensaje construido puede tener ya una representación en la base de datos de cuadro de mensajes si asigna partes de un mensaje que ya está confirmado.</span><span class="sxs-lookup"><span data-stu-id="b1e93-114">A constructed message may already have a representation in the MessageBox database if you assign parts from a message that is already committed.</span></span>  
  
 <span data-ttu-id="b1e93-115">Por ejemplo, el código siguiente envía los datos de UnderlyingPart desde la representación que se encuentra en la base de datos de cuadro de mensajes:</span><span class="sxs-lookup"><span data-stu-id="b1e93-115">For example, the following code sends the UnderlyingPart data from the representation in the MessageBox database:</span></span>  
  
```  
// In this example, assume m1 is committed to the MessageBox  
Construct m2 {   
               m2 = m1; // m2’s part data representation is the UnderlyingPart data of m1  
               m2(myContextProperty) = “123”; // m2’s part data representation is still the UnderlyingPart data of m1  
               A.test(m2.part); // orchestration engine does not invalidate the UnderlyingPart MessageBox representation  
             }  
Send(p.o, m2);  
```  
  
 <span data-ttu-id="b1e93-116">En lugar de utilizar el código de usuario anterior, se puede utilizar código parecido al siguiente para devolver un documento XmlDocument a una variable XLANG de mensaje:</span><span class="sxs-lookup"><span data-stu-id="b1e93-116">Instead of using the preceding user code, you can use code that is similar to the following to return an XmlDocument document to a Message XLANG variable:</span></span>  
  
```  
Void A.test(ref XmlDocument xd) {…}  
XmlDocument B.test(XmlDocument xd) {…}  
construct m2 {  
               m2 = m1;  
               m2(myContextProperty) = “123”; // m2’s part data representation is the UnderlyingPart data of m1  
               A.test(ref m2.part); // orchestration engine has enough information to know it has to invalidate the UnderlyingPart MessageBox representation  
               // or  
               m2.part = B.test(m2.part); // orchestration engine has enough information to know it has to invalidate the UnderlyingPart MessageBox representation  
             }  
```