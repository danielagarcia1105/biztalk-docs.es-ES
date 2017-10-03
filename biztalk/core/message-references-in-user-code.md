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
# <a name="message-references-in-user-code"></a>Referencias de mensajes en código de usuario
Cuando se construye un mensaje, una representación de éste se encuentra en la base de datos de cuadro de mensajes y otra en la memoria del equipo. Si se realiza la asignación del mensaje pasando una referencia del mensaje a un objeto .NET o a un ensamblado externo y, a continuación, uno de ellos modifica la representación que se encuentra en la memoria del equipo, el motor de orquestaciones de BizTalk no tendrá constancia de la modificación.  
  
 Además, el motor de orquestaciones no invalida los datos de partes del mensaje que se encuentran en la representación de la base de datos de cuadro de mensajes. Estos datos cuentan con los siguientes modos de representación:  
  
-   Representación XmlDocument  
  
-   Representación de objetos  
  
-   Representación de secuencias  
  
-   Representación UnderlyingPart  
  
 El modo en que los datos de partes del mensaje se representen en la memoria dependerá de la construcción del mensaje y de si el tipo es una clase .NET o un esquema en lenguaje de definición de esquemas XML (XSD). Sin embargo, la representación UnderlyingPart siempre es una secuencia que apunta a la base de datos de cuadro de mensajes. Puesto que los mensajes en BizTalk Server son inmutables una vez confirmado el mensaje en la base de datos de cuadro de mensajes, el motor de orquestaciones utiliza la representación de esta base de datos para hacer referencia a los datos de partes del mensaje.  
  
> [!NOTE]
>  Un mensaje construido puede tener ya una representación en la base de datos de cuadro de mensajes si asigna partes de un mensaje que ya está confirmado.  
  
 Por ejemplo, el código siguiente envía los datos de UnderlyingPart desde la representación que se encuentra en la base de datos de cuadro de mensajes:  
  
```  
// In this example, assume m1 is committed to the MessageBox  
Construct m2 {   
               m2 = m1; // m2’s part data representation is the UnderlyingPart data of m1  
               m2(myContextProperty) = “123”; // m2’s part data representation is still the UnderlyingPart data of m1  
               A.test(m2.part); // orchestration engine does not invalidate the UnderlyingPart MessageBox representation  
             }  
Send(p.o, m2);  
```  
  
 En lugar de utilizar el código de usuario anterior, se puede utilizar código parecido al siguiente para devolver un documento XmlDocument a una variable XLANG de mensaje:  
  
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