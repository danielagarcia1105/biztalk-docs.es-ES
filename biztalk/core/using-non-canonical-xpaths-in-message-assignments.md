---
title: Usar XPaths no canónicos en las asignaciones de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 052d1d72-43ce-4654-bf29-86f82ad65e91
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f35d946ff595fa4d85427c7b3d6be81247cedf68
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977863"
---
# <a name="using-non-canonical-xpaths-in-message-assignments"></a>Usar XPaths no canónicos en las asignaciones de mensajes
Si se utilizan partes de mensaje de .Net, es posible anotar el código con el atributo de serialización XML que, cuando también se acompaña con anotaciones de propiedad o campos distintivos, puede tener como resultado expresiones de XPath de considerable complejidad. Es posible que estas expresiones complejas de XPath sean no canónicas. solo se debería utilizar XPath no canónico en orquestaciones de enlace directo; es posible que se produzcan errores con orquestaciones enlazadas lógica o físicamente. Las orquestaciones de enlace directo no se basan en una canalización para procesar el documento XML; en consecuencia, todo el documento XML se carga en la memoria antes del procesamiento.  
  
## <a name="canonical-and-non-canonical-xpath"></a>XPath canónico y no canónico  
 Canónico o abreviada de XPath utiliza la sintaxis abreviada de la especificación de XPath ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) para especificar una ruta de acceso de ubicación. Entre las propiedades distintivas de expresiones de XPath canónico se incluyen las siguientes:  
  
- El `child::` eje se establece como valor predeterminado para cada paso de la expresión  
  
- `@` es la abreviatura de `attribute::`.  
  
- `//` es la abreviatura de `/descendant-or-self::node()/`.  
  
- `.` es la abreviatura de `self::node()`.  
  
- `..` es la abreviatura de `parent::node()`.  
  
  Las expresiones XPath canónicas son expresiones simples, como `/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`.  
  
  Esto contrasta con la forma no canónica de XPath. Este formulario es también conocida como la "forma general" o "XPath arbitrario" y se distingue mediante expresiones arbitrariamente complejas y pueden combinar varios ejes: `//element-name//*[local-name()='element-name' and position()=2]`.  
  
## <a name="example"></a>Ejemplo  
 Observe el programa siguiente:  
  
```  
using System;  
using System.IO;  
using System.Xml.Serialization;  
using Microsoft.XLANGs.BaseTypes;  
  
namespace ComplexNetXPath  
{  
    public class Animal  
    {  
        [Property( typeof(BTS.RetryCount) )]  
        public int NumberOfLegs;  
    }   
    public class Snake : Animal  
    {  
        public Snake()  
        {  
            NumberOfLegs = 0;  
        }  
    }   
    public class Dog : Animal  
    {  
        public Dog()  
        {  
            NumberOfLegs = 4;  
        }  
    }   
    public class Zoo  
    {  
        //  
        // Dogs and snakes are the possible animals of  
        // the week.  
        //  
        [XmlElement(typeof(Snake))]  
        [XmlElement(typeof(Dog))]  
        public Animal AnimalOfTheWeek;  
    }  
    class Class1  
    {  
        static void Main(string[] args)  
        {  
            XmlSerializer ser = new XmlSerializer(typeof(Zoo));  
            Stream s = Console.OpenStandardOutput();  
            Zoo z = new Zoo();  
            z.AnimalOfTheWeek = new Dog();  
            ser.Serialize( s, z );  
            s.Flush();  
            Console.WriteLine("------------------");  
            z.AnimalOfTheWeek = new Snake();  
            ser.Serialize( s, z );  
            s.Flush();  
        }  
    }  
}   
```  
  
 El tipo Zoo contiene un campo Animal que puede ser Snake o Dog. La instancia Animal tiene un campo NumberOfLegs que se anota con PropertyAttribute, con lo que la propiedad BTS.RetryCount se asigna a este campo.  
  
> [!NOTE]
>  Una aplicación real definiría sus propias propiedades.  
  
 Cuando el animal de la semana es Dog, la instancia de Zoo serializada tiene el siguiente aspecto:  
  
```  
<Zoo>  
  <Dog>  
    <NumberOfLegs>4</NumberOfLegs>  
  </Dog>  
</Zoo>   
```  
  
 Cuando el animal de la semana es Snake, la instancia de Zoo serializada tiene el siguiente aspecto:  
  
```  
<Zoo>  
  <Snake>  
    <NumberOfLegs>0</NumberOfLegs>  
  </Snake>  
</Zoo>  
```  
  
 Al considerar el esquema XML equivalente a la clase de .Net Zoo, la expresión de XPath para seleccionar la propiedad RetryCount permitiría la aparición de un paso Snake o Dog en la ruta de la propiedad:  
  
```  
/*[local-name()='Zoo' and namespace-uri()='']/*[(local-name()='Dog' and namespace-uri()='') or (local-name()='Snake' and namespace-uri()='')]/*[local-name()='NumberOfLegs' and namespace-uri()='']  
```  
  
 Los componentes de canalización XML no pueden controlar esta expresión de XPath no canónico. Para evitar esta situación, los atributos de serialización XML de varias opciones de tipo test no deberían utilizarse junto con las canalizaciones XML; además, se debería tener cuidado al utilizar los siguientes atributos de serialización XML:  
  
-   XmlElementAttribute  
  
-   XmlAttributeAttribute  
  
-   XmlArrayItemAttribute