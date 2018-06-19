---
title: Mensajes representan como clases .NET | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- orchestrations, filters
ms.assetid: cdbea200-552e-4734-a370-2f93da07ea81
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f0ea95f02de6e9fda411fa0183569dc0779033
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263396"
---
# <a name="messages-represented-as-net-classes"></a><span data-ttu-id="07d74-102">Mensajes representados como clases .NET</span><span class="sxs-lookup"><span data-stu-id="07d74-102">Messages Represented as .NET Classes</span></span>
<span data-ttu-id="07d74-103">Este enfoque implica en primer lugar la creación de una clase .NET que defina el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="07d74-103">This approach first involves creating a .NET class that defines your message type.</span></span> <span data-ttu-id="07d74-104">La clase deberá tener un constructor predeterminado para que se compile la orquestación que la usa.</span><span class="sxs-lookup"><span data-stu-id="07d74-104">The class must have a default constructor or the orchestration using it will not compile.</span></span> <span data-ttu-id="07d74-105">A continuación se muestra un ejemplo sencillo de dicha clase.</span><span class="sxs-lookup"><span data-stu-id="07d74-105">A simple example of such a class is shown here.</span></span>  
  
```  
using System;  
using Microsoft.XLANGs.BaseTypes;  
Using PropertyNamespace;  
  
namespace NetClass  
{  
   [Serializable]  
   public class MsgClass  
   {  
      public MsgClass()  
      {  
         StrField = "OK";  
         IntField = 1;  
         ShortField = 1;  
      }  
  
      [PropertyNamespace.ShortPropertyName]  
      public Int16 ShortField;  
  
      [PropertyAttribute(typeof(PropertyNamespace.StringPropertyName)]  
      [DistinguishedFieldAttribute()]  
      public String StrField;  
  
      [DistinguishedFieldAttribute()]  
      public int IntField;  
   }  
}  
```  
  
 <span data-ttu-id="07d74-106">En el ejemplo anterior, ShortField sería una propiedad de tipo PropertyNamespace.ShortPropertyName y el tipo subyacente de la propiedad tendría que ser Int16, que es el tipo de ShortField.</span><span class="sxs-lookup"><span data-stu-id="07d74-106">In the above example, ShortField would be a property of type PropertyNamespace.ShortPropertyName and the underlying type of the property would have to be Int16 which is the type of ShortField.</span></span> <span data-ttu-id="07d74-107">StrField sería tanto un campo distinguido como una propiedad de tipo PropertyNamespace.StringPropertyName, y el tipo subyacente de la propiedad tendría que ser de tipo String, que es el tipo de StrField.</span><span class="sxs-lookup"><span data-stu-id="07d74-107">StrField would be both a distinguished field and a property of type PropertyNamespace.StringPropertyName and the underlying type of the property would have to be type of String which is the type of StrField.</span></span> <span data-ttu-id="07d74-108">Normalmente, PropertyNamespace.StringPropertyName y PropertyNamespace.ShortPropertyName se crearían como propiedades de esquema mediante el Editor de esquemas de BizTalk, y deberá hacer referencia al ensamblado que contiene las propiedades de esquema en el proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="07d74-108">Normally both PropertyNamespace.StringPropertyName and PropertyNamespace.ShortPropertyName would be created through the BizTalk Schema Editor as schema properties, and you need to reference the assembly which contains the schema properties in your C# project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07d74-109">En el lenguaje de programación C#, la parte final Attribute de un nombre de atributo es opcional, por lo que puede omitir dicha parte final y usar en su lugar DistinguishedField o Property.</span><span class="sxs-lookup"><span data-stu-id="07d74-109">In C# programming language, the Attribute ending of an attribute name is optional, so you can omit the Attribute ending and use DistinguishedField or Property instead.</span></span> <span data-ttu-id="07d74-110">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="07d74-110">For example,</span></span>  
  
```  
[Property(typeof(PropertyNamespace.StringPropertyName))]  
[DistinguishedField]  
public string StrField;  
```  
  
 <span data-ttu-id="07d74-111">Una vez definido el tipo de mensaje, es muy sencillo escribir código en la orquestación para crear un nuevo mensaje de este tipo.</span><span class="sxs-lookup"><span data-stu-id="07d74-111">Once the message type is defined, it is very easy to write code in the orchestration that will create a new message of this type.</span></span> <span data-ttu-id="07d74-112">Dentro de un **construir mensaje** forma, escribir expresiones simples para crear un nuevo mensaje de la **MsgClass** escriba se muestra anteriormente y, a continuación, asignar valores a los campos que tienen el atributo como completos Campos (si desea invalidar los valores predeterminados).</span><span class="sxs-lookup"><span data-stu-id="07d74-112">Within a **Construct Message** shape, you write simple expressions to create a new message of the **MsgClass** type shown above, and then assign values to the fields which are attributed as Distinguished Fields (if you wish to override the default values).</span></span> <span data-ttu-id="07d74-113">Observe que MyMsg es una variable de mensaje de orquestación del tipo NetClass.MsgClass.</span><span class="sxs-lookup"><span data-stu-id="07d74-113">Note that MyMsg is an orchestration message variable whose type is NetClass.MsgClass.</span></span>  
  
```  
MyMsg = new NetClass.MsgClass();  
MyMsg.StrField = "Changed Value";  
MyMsg.IntField = 15;  
```  
  
## <a name="see-also"></a><span data-ttu-id="07d74-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="07d74-114">See Also</span></span>  
 <span data-ttu-id="07d74-115">[Mensajes representados como esquemas XSD](../core/messages-represented-as-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="07d74-115">[Messages Represented as XSD Schemas](../core/messages-represented-as-xsd-schemas.md) </span></span>  
 <span data-ttu-id="07d74-116">[Mensajes representados como XLANGMessage](../core/messages-represented-as-xlangmessage.md) </span><span class="sxs-lookup"><span data-stu-id="07d74-116">[Messages Represented as XLANGMessage](../core/messages-represented-as-xlangmessage.md) </span></span>  
 [<span data-ttu-id="07d74-117">Construir mensajes en el código de usuario</span><span class="sxs-lookup"><span data-stu-id="07d74-117">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)