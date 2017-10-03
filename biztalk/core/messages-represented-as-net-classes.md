---
title: Mensajes representan como clases .NET | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- orchestrations, filters
ms.assetid: cdbea200-552e-4734-a370-2f93da07ea81
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f0ea95f02de6e9fda411fa0183569dc0779033
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messages-represented-as-net-classes"></a>Mensajes representados como clases .NET
Este enfoque implica en primer lugar la creación de una clase .NET que defina el tipo de mensaje. La clase deberá tener un constructor predeterminado para que se compile la orquestación que la usa. A continuación se muestra un ejemplo sencillo de dicha clase.  
  
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
  
 En el ejemplo anterior, ShortField sería una propiedad de tipo PropertyNamespace.ShortPropertyName y el tipo subyacente de la propiedad tendría que ser Int16, que es el tipo de ShortField. StrField sería tanto un campo distinguido como una propiedad de tipo PropertyNamespace.StringPropertyName, y el tipo subyacente de la propiedad tendría que ser de tipo String, que es el tipo de StrField. Normalmente, PropertyNamespace.StringPropertyName y PropertyNamespace.ShortPropertyName se crearían como propiedades de esquema mediante el Editor de esquemas de BizTalk, y deberá hacer referencia al ensamblado que contiene las propiedades de esquema en el proyecto de C#.  
  
> [!NOTE]
>  En el lenguaje de programación C#, la parte final Attribute de un nombre de atributo es opcional, por lo que puede omitir dicha parte final y usar en su lugar DistinguishedField o Property. Por ejemplo,  
  
```  
[Property(typeof(PropertyNamespace.StringPropertyName))]  
[DistinguishedField]  
public string StrField;  
```  
  
 Una vez definido el tipo de mensaje, es muy sencillo escribir código en la orquestación para crear un nuevo mensaje de este tipo. Dentro de un **construir mensaje** forma, escribir expresiones simples para crear un nuevo mensaje de la **MsgClass** escriba se muestra anteriormente y, a continuación, asignar valores a los campos que tienen el atributo como completos Campos (si desea invalidar los valores predeterminados). Observe que MyMsg es una variable de mensaje de orquestación del tipo NetClass.MsgClass.  
  
```  
MyMsg = new NetClass.MsgClass();  
MyMsg.StrField = "Changed Value";  
MyMsg.IntField = 15;  
```  
  
## <a name="see-also"></a>Vea también  
 [Mensajes representados como esquemas XSD](../core/messages-represented-as-xsd-schemas.md)   
 [Mensajes representados como XLANGMessage](../core/messages-represented-as-xlangmessage.md)   
 [Construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md)