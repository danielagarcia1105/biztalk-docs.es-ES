---
title: Optimizar el rendimiento de la orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 437c7325-f037-451a-8dbd-f8d8c8889e20
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 473c6e904def7f58adcb52eb26e46891be9c41d0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971885"
---
# <a name="optimizing-orchestration-performance"></a>Optimizar el rendimiento de orquestación
En este tema se describe los procedimientos recomendados para usar las orquestaciones en soluciones de BizTalk Server. Esto incluye recomendaciones para:  
  
-   Reducir la latencia de las soluciones de BizTalk Server que utilizan las orquestaciones  
  
    -   Eliminación de orquestaciones para que sólo los patrones de mensajería  
  
    -   Uso en línea envía desde las orquestaciones  
  
    -   Minimizar los puntos de persistencia de orquestación  
  
-   Anidación de orquestaciones  
  
-   Patrones de diseño de orquestación  
  
-   Bloques de control de excepciones de orquestación  
  
## <a name="recommendations-for-optimizing-orchestrations-for-low-latency-scenarios"></a>Recomendaciones para optimizar las orquestaciones para escenarios de baja latencia  
 Las técnicas siguientes pueden usarse para reducir la latencia de las soluciones de BizTalk Server que utilizan las orquestaciones.  
  
### <a name="eliminate-orchestrations-for-messaging-only-patterns"></a>Eliminar las orquestaciones para que sólo los patrones de mensajería  
 Cuando sea posible minimizar el uso de orquestaciones para aumentar el rendimiento global y reducir la latencia de procesos empresariales. Si es necesario ejecutar largo transacciones de ejecución y no es necesario para invocar varios sistemas para cada solicitud, a continuación, considere la posibilidad de eliminar las orquestaciones y mover la lógica de negocios a puertos de envío y recepción para reducir la cantidad total de ida y vuelta a la BizTalkMsgBoxDb y reducir la latencia debido al acceso a la base de datos. En este caso, implementar canalizaciones personalizadas y volver a usar las clases auxiliares que anteriormente se invocaron desde las orquestaciones. Usar las orquestaciones solo cuando sea estrictamente necesario para implementar patrones de diseño como de dispersión y recopilación o convoyes. Para obtener más información sobre los patrones de diseño de orquestación, vea el tema [implementar patrones de diseño de orquestaciones](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) en la documentación de BizTalk Server.  
  
### <a name="use-inline-sends-from-orchestrations-to-accommodate-low-latency-scenarios"></a>Usar en línea se envía desde las orquestaciones para dar cabida a escenarios de baja latencia  
 Siempre que sea posible, minimice el uso de las orquestaciones y favorecer patrones únicamente de mensajería para aumentar el rendimiento general y reducir la latencia de los procesos empresariales. Si no es necesario para las transacciones de larga ejecución y no es necesario para la lógica de negocios invocar varios sistemas, a continuación, considere la posibilidad de mover la lógica de negocios a los puertos de envío y recepción y eliminación del uso de las orquestaciones. Este enfoque puede implementarse con canalizaciones personalizadas y que volver a usar las clases auxiliares que anteriormente se invocaron desde las orquestaciones. Con el fin de lograr un mejor rendimiento en escenarios de baja latencia, puede adoptar uno de los enfoques siguientes:  
  
-   Eliminar orquestaciones innecesarias y adopte patrones únicamente de mensajería para reducir la cantidad total de ida y vuelta a la base de datos de BizTalk MessageBox. Este enfoque contempla una latencia baja porque envía insertada omitir el asociado y motor de mensajería de BizTalk sobrecarga. Se proporciona la funcionalidad de envío de orquestación en línea con BizTalk Server 2006 y versiones posteriores.  
  
-   Dentro de orquestaciones, eliminar los puertos lógicos que se enlaza a los puertos físicos y uso en línea se envía en su lugar. Por ejemplo, un envío en línea podría usarse para crear una instancia de una clase de proxy WCF para invocar un servicio Web auxiliar o un componente ADO.NET para tener acceso a una base de datos de SQL Server. En el diagrama siguiente, se realiza un envío en línea cuando la orquestación crea una instancia de un componente empresarial, que internamente hace uso de WCF objeto de proxy para llamar directamente a un servicio Web auxiliar:  
  
     ![Representación de envío en línea de orquestación de BizTalk](../technical-guides/media/inlinesend.gif "InlineSend")  
  
> [!NOTE]
>  Aunque el uso de los envíos en línea desde las orquestaciones reducirá significativamente la latencia, existen limitaciones en este enfoque. Dado que los envíos en línea omiten el motor de mensajería de BizTalk, no está disponible la siguiente funcionalidad proporcionada con el motor de mensajería:  
> 
> - Canalizaciones transaccionales.  
>   -   Canalizaciones recuperables  
>   -   Canalizaciones que llaman a la API de interceptor de BAM  
>   -   Compatibilidad del adaptador de BizTalk Server  
>   -   Procesar por lotes  
>   -   Reintentos  
>   -   Conjunto de correlaciones de inicialización  
>   -   Configuración declarativa  
>   -   Transportes secundarios  
>   -   Seguimiento  
>   -   Uso declarativo de BAM  
  
 Para obtener más información sobre los tipos de canalizaciones que no se puede ejecutar desde una orquestación, consulte la sección "Restricciones" del tema [cómo usar expresiones para ejecutar canalizaciones](http://go.microsoft.com/fwlink/?LinkId=158008) (http://go.microsoft.com/fwlink/?LinkId=158008) en el servidor BizTalk Server documentación de 2010.  
  
### <a name="optimize-orchestration-latency-by-reducing-the-number-of-persistence-points-if-possible"></a>Optimizar la latencia de la orquestación al reducir el número de puntos de persistencia, si es posible  
 Un ámbito de la orquestación sólo debe estar marcada como "transaccional de larga ejecución" Si desea utilizar tiempos de espera de compensación o ámbito. Un ámbito transaccional de larga ejecución hace que un punto de persistencia adicional al final del ámbito, por lo que debe evitarse cuando no necesite usar la compensación o tiempos de espera de ámbito. Un ámbito atómico hace que un punto de persistencia al final del ámbito, pero también garantiza que no se produzca ningún punto de persistencia dentro del ámbito atómico. Este efecto secundario de ninguna persistencia dentro del ámbito a veces puede utilizarse para su beneficio a los puntos de persistencia de lote (al realizar varias envía, por ejemplo). En general, sin embargo, se recomienda evitar los ámbitos atómicos si es posible. El motor de orquestaciones guarda en almacenamiento persistente todo el estado de una instancia de orquestación de ejecución en varios puntos, para que la instancia más adelante se puede restaurar en la memoria y lleva a cabo hasta su finalización.   
**El número de puntos de persistencia en una orquestación es uno de los factores claves que influyen en la latencia de mensajes que fluyen a través de orquestaciones**. Cada vez que el motor alcanza un punto de persistencia, se serializa el estado interno de una orquestación en ejecución y se guarda en el cuadro de mensajes y esta operación implica un costo de latencia. La serialización del estado interno incluye todos los mensajes y variables que crea una instancia y aún no se han publicado en la orquestación. Cuanto mayor sea el mensajes y las variables y mayor es el número de estos, cuanto más tiempo se tardará en conservar el estado interno de una orquestación. Un número excesivo de puntos de persistencia puede provocar una degradación del rendimiento significativa. Por este motivo, se recomienda la eliminación de puntos de persistencia innecesarios desde las orquestaciones al reducir el número de ámbitos transaccionales y formas envío. Este enfoque permite reducir la contención en el cuadro de mensajes debido a la deshidratación de orquestaciones y rehidratación, aumentar la escalabilidad global y reducir la latencia de la orquestación.   
Otra recomendación es mantener siempre el estado interno de una orquestación tan pequeña como sea posible. Esta técnica puede reducir significativamente el tiempo empleado por el motor XLANG serializar, guardar y restaurar el estado interno de una orquestación en el caso de punto de persistencia. Una manera de conseguirlo es crear variables y mensajes tan tarde como sea posible y liberarlos tan pronto como sea posible; Por ejemplo, introducir los ámbitos no transaccionales dentro de las orquestaciones y declarar variables y mensajes dentro de estos ámbitos internos en lugar de declarar a ellos en el nivel superior. Para obtener más información acerca de cómo minimizar los puntos de persistencia de orquestación, vea los temas siguientes en la documentación de BizTalk Server 2010:  
  
-   [Persistencia y el motor de orquestaciones](http://go.microsoft.com/fwlink/?LinkID=155292) (http://go.microsoft.com/fwlink/?LinkID=155292).  
  
-   [Orquestación deshidratación y rehidratación](http://go.microsoft.com/fwlink/?LinkID=155284) (http://go.microsoft.com/fwlink/?LinkID=155292).  
  
## <a name="guidelines-for-using-promoted-properties-to-access-message-tags-or-attributes-from-an-orchestration"></a>Directrices para usar promocionan propiedades, atributos o las etiquetas de mensaje de acceso desde una orquestación  
 Si es necesario promocionar propiedades, promocionar solo las propiedades que se usan para el enrutamiento de mensajes, filtros y correlación de mensajes. La promoción de cada propiedad requiere el componente de desensamblador (personalizada de formato, XML,) para reconocer el tipo de documento y recuperar datos desde el mensaje mediante la expresión XPath de la anotación relativa contenida en el esquema XSD que define el tipo de documento. Además, cada promoción de propiedades hace una llamada independiente del procedimiento almacenado de bts_InsertProperty cuando el agente de mensaje se publica el mensaje en la base de datos de cuadro de mensajes. Si una orquestación necesita tener acceso a un elemento o atributo concreto contenidos en un documento XML, utilice una de las técnicas siguientes:  
  
- Reduzca el número de propiedades promocionadas y escritos y eliminar aquellas que no son estrictamente necesarios.  
  
- Eliminar campos distintivos innecesarios. Los campos distintivos se escriben las propiedades de contexto y fácilmente que pueden ocupar espacio significativo como su nombre es igual a la expresión XPath que se usa para recuperar datos. La propiedad distintivo se define como anotaciones en el esquema XSD que define el tipo de documento. El componente de desensamblador usa el mismo enfoque adoptado para las propiedades promocionadas y la expresión XPath que define un campo distintivo para buscarlo en el documento entrante. A continuación, el componente de desensamblador escribe una propiedad en el contexto donde:  
  
  - **Nombre**: expresión XPath definida en la anotación.  
  
  - **Valor**: valor del elemento identificado por la expresión XPath dentro de un documento entrante.  
  
    Las expresiones XPath pueden ser muy largos, especialmente cuando el elemento en cuestión es muy profundo en el esquema del documento. Por lo que más distinguen los campos, cuanto mayor sea el tamaño del contexto. Esto afecta negativamente a su vez el rendimiento general.  
  
- Use la función integrada XPath proporcionada por el tiempo de ejecución de la orquestación.  
  
- Si los mensajes son bastante pequeños (unos pocos kilobytes) y con formato XML, puede deserializar el mensaje en una instancia de la clase de .NET y trabajar con campos públicos y propiedades. Si el mensaje una elaboración complejo (código personalizado, las directivas del motor de reglas de negocio, etc.) debe tener acceso a datos mediante las propiedades expuestas por una instancia de una clase .NET es mucho más rápido con expresiones XPath. Cuando haya finalizado la lógica de negocios invocada por la orquestación, se puede serializar el objeto de entidad en un mensaje de BizTalk. Puede crear clases de .NET desde un esquema XML utilizando una de las siguientes herramientas: herramienta XSD (.NET Framework 2.0) o SVCUTIL (.NET Framework 3.0).  
  
- Habilitar un componente de aplicación auxiliar desde una orquestación. Esta técnica tiene la ventaja con respecto a los campos distintivos. De hecho, una orquestación puede leer el XPath expresión desde un archivo de configuración almacenar (archivo de configuración, SSO Config Store, base de datos personalizado etc.), por lo tanto, cuando se tiene que cambiar la expresión XPath, no es necesario cambiar y volver a implementar un esquema, que debe hacer para las propiedades promocionadas y d istinguished campos. Ejemplo de código siguiente proporciona un ejemplo de un componente de aplicación auxiliar. El componente utiliza la clase XPathReader proporcionada por el tiempo de ejecución de BizTalk. Esto permite al código que leerá la secuencia de documentos hasta que se encuentra la expresión XPath.  
  
```  
#region Copyright  
//===  
//Microsoft Windows Server AppFabric Customer Advisory Team (CAT)   
//  
// This sample is supplemental to the technical guidance published on the community  
// blog.  
//   
// Author: Paolo Salvatori.  
//===  
// Copyright © 2010 Microsoft Corporation. All rights reserved.  
//   
// THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER   
// EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE IMPLIED WARRANTIES OF   
// MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. YOU BEAR THE RISK OF USING IT.  
//===  
#endregion  
#region Using Directives  
using System;  
using System.Collections.Generic;  
using System.IO;  
using System.Xml;  
using System.Linq;  
using System.Text;  
using System.Globalization;  
using Microsoft.XLANGs.BaseTypes;   
using Microsoft.BizTalk.Streaming;  
using Microsoft.BizTalk.XPath;  
#endregion  
namespace Microsoft.AppFabric.CAT.Samples.DuplexMEP.Helpers  
{  
public class XPathHelper  
{  
#region Private Constants   
private const string MessageCannotBeNull = "[XPathReader] The message cannot be null.";  
#endregion  
#region Public Static Methods  
public static string GetValue(XLANGMessage message, int partIndex, string xpath)  
{  
try  
{  
if (message == null)  
{  
throw new ApplicationException(MessageCannotBeNull);  
}  
using (Stream stream = message[partIndex].RetrieveAs(typeof(Stream)) as Stream)  
{  
XmlTextReader xmlTextReader = new XmlTextReader(stream);  
XPathCollection xPathCollection = new XPathCollection();  
XPathReader xPathReader = new XPathReader(xmlTextReader, xPathCollection);  
xPathCollection.Add(xpath);  
while (xPathReader.Read())  
{  
if (xPathReader.HasAttributes)  
{  
for (int i = 0; i < xPathReader.AttributeCount; i++)  
{  
xPathReader.MoveToAttribute(i);  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.GetAttribute(i);  
}  
}  
}  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.ReadString();  
}  
}  
}  
}  
finally  
{  
message.Dispose();  
}  
return string.Empty;  
}  
#endregion  
}  
}  
```  
  
## <a name="minimize-orchestration-complexity-to-improve-performance"></a>Minimizar la complejidad de la orquestación para mejorar el rendimiento  
 La complejidad de las orquestaciones tiene un impacto significativo en el rendimiento. A medida que aumenta la complejidad de la orquestación, se reduce el rendimiento general. Las orquestaciones se pueden usar en una variedad casi infinita de escenarios, y cada escenario puede implicar las orquestaciones de complejidad variable. Evite las orquestaciones complejas cuando sea posible en favor de un enfoque modular. En otras palabras, dividir la lógica de negocios en varias orquestaciones reutilizables.  
  
 Si es necesario implementar una orquestación compleja, definir mensajes y variables en los ámbitos internos siempre que sea posible en lugar de en el nivel raíz. Esta técnica mantiene una superficie menor en la memoria para cada orquestación porque las variables y los mensajes se eliminan cuando el flujo sale del ámbito en el que se definieron las variables y mensajes. Este enfoque resulta especialmente útil cuando las orquestaciones se guardan en el cuadro de mensajes en puntos de persistencia.  
  
## <a name="use-the-call-orchestration-shape-versus-the-start-orchestration-shape-to-improve-performance"></a>Utilice la forma de orquestación de llamada frente a la forma Iniciar orquestación para mejorar el rendimiento  
 Evitar la **Iniciar orquestación** y dar forma a utilizar el **orquestación de llamada** forma para ejecutar una orquestación anidada. De hecho, el **orquestación de llamada** forma puede usarse para llamar sincrónicamente a una orquestación que se hace referencia en otro proyecto. Este enfoque permite la reutilización de los patrones comunes de flujo de trabajo de orquestación en proyectos de BizTalk. Cuando se invoca otra orquestación anidada de forma sincrónica con el **orquestación de llamada** forma, la orquestación envolvente espera a que la orquestación anidada finalice antes de continuar. La orquestación anidada se ejecuta en el mismo subproceso que se ejecuta la orquestación de llamada.  
  
 El **Iniciar orquestación** forma es similar a la **orquestación de llamada** forma, pero en este caso la orquestación anidada se denomina de forma asincrónica: el flujo de control en la invocación orquestación continúa más allá de la invocación, sin esperar a la orquestación invocada termine. Para implementar esta separación entre el llamador y las orquestaciones llamadas, el **Iniciar orquestación** se implementa a través de la publicación de un mensaje a BizTalk Messagebox. Este mensaje, a continuación, se consume por una instancia de host de BizTalk en el proceso que ejecuta la orquestación anidada. Cuando sea posible, use **orquestación de llamada**, especialmente si la orquestación de llamada debe esperar un resultado de la orquestación anidada con el fin de continuar el procesamiento.  Para obtener más información sobre el uso de la forma orquestación de llamada, vea los temas siguientes en la documentación de BizTalk Server 2010:  
  
-   [Trabajar con puertos de enlace directo en orquestaciones](http://go.microsoft.com/fwlink/?LinkId=139902) (http://go.microsoft.com/fwlink/?LinkId=139902).  
  
-   [Anidar orquestaciones](http://go.microsoft.com/fwlink/?LinkId=139903) (http://go.microsoft.com/fwlink/?LinkId=139903).  
  
## <a name="use-xmlreader-with-xlangmessage-versus-using-xmlreader-with-xmldocument-to-improve-orchestration-performance"></a>Uso de XmlReader con XLANGMessage frente al uso de XmlReader con XmlDocument para mejorar el rendimiento de la orquestación  
 Para mejorar el rendimiento de las orquestaciones para los métodos de .NET que se llama desde una orquestación, utilice XmlReader con XLANGMessage, no XmlDocument. En el ejemplo de código siguiente se ilustra esta funcionalidad.  
  
```csharp  
// As a general rule, use XmlReader with XLANGMessage, not XmlDocument.   
// This is illustrated in the parameter passed into the following code.   
// The XLANG/s compiler doesn't allow a return value of XmlReader   
// so documents must be initially constructed as XmlDocument()  
public static XmlDocument FromMsg(XLANGMessage old)  
{  
    //get at the data  
    XmlDocument ret = new XmlDocument();  
  
    try{  
        XmlReader reader = (XmlReader)old[0].RetrieveAs(typeof(XmlReader));  
        //construct new message from old  
        //read property  
        object msgid = old.GetPropertyValue(typeof(BTS.MessageID));  
    }  
    finally {  
        // Call Dispose on the XLANGMessage object   
        // because the message doesn't belong to the   
        // .NET runtime - it belongs to the Messagebox database   
        old.Dispose();  
    }  
    return ret;  
}  
```  
  
 Otro método sería crear una clase .NET en función del esquema. Este proceso tarda menos memoria que carga el documento en un **XmlDocument** objeto, así como proporcionar un acceso sencillo a los elementos de esquema para los desarrolladores de .NET. Para generar una clase basada en un esquema de BizTalk, puede usar la herramienta xsd.exe incluida con Visual Studio. Por ejemplo, ejecutar **xsd.exe \<schema.xsd\> /classes** contra un esquema simple que contiene campos denominados ItemA, ItemB, ItemC, generará la siguiente clase.  
  
```csharp  
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:2.0.50727.1433  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
using System.Xml.Serialization;  
  
//   
// This source code was auto-generated by xsd, Version=2.0.50727.42.  
//  
  
/// <remarks/>  
[System.CodeDom.Compiler.GeneratedCodeAttribute("xsd", "2.0.50727.42")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://Schemas.MySchema")]  
[System.Xml.Serialization.XmlRootAttribute(Namespace="http://Schemas.MySchema", IsNullable=false)]  
public partial class MySchemaRoot {  
  
    private string itemAField;  
  
    private string itemBField;  
  
    private string itemCField;  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemA {  
        get {  
            return this.itemAField;  
        }  
        set {  
            this.itemAField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemB {  
        get {  
            return this.itemBField;  
        }  
        set {  
            this.itemBField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemC {  
        get {  
            return this.itemCField;  
        }  
        set {  
            this.itemCField = value;  
        }  
    }  
}  
```  
  
 Esta clase, a continuación, se puede hacer referencia en el ensamblado de .NET para tener acceso a los elementos del mensaje y el objeto devuelto se puede asignar directamente a un mensaje. El siguiente es un ejemplo del uso de la clase generada anteriormente.  
  
```csharp  
public static Root SetValues(Microsoft.XLANGs.BaseTypes.XLANGMessage msg)  
{  
   try  
   {  
   MySchemaRoot rootObj=(MySchemaRoot)msg[0].RetrieveAs(typeof(MySchemaRoot);  
   rootObj.ItemA="value a";  
   rootObj.ItemB="value b";  
   rootObj.ItemC="value c";  
   }  
    finally {  
        msg.Dispose();  
            }  
  
   return rootObj;  
}  
```  
  
 Esta técnica permite usar un enfoque orientado al procesar los mensajes. Esta técnica debe usarse principalmente con mensajes relativamente pequeños. Esto es porque, aunque esta técnica usa considerablemente menos memoria que al cargar el mensaje en una **XmlDocument** objeto, el mensaje completo se siga estando cargado en memoria. Al procesar los mensajes más grandes, utilice el **XmlReader** clase para leer mensajes y el **XmlWriter** clase para escribir mensajes. Cuando se usa **XmlReader** y **XmlWriter**, el mensaje está contenido en un **VirtualStream** objeto. Si el tamaño del mensaje supera el valor especificado para **umbral de mensajes grandes (bytes)** que se expone en la página de configuración de propiedades del grupo de BizTalk, el mensaje se escribe en el sistema de archivos. Esto disminuye el rendimiento global, pero evita las excepciones de memoria insuficiente.  
  
## <a name="improve-performance-by-minimizing-the-use-of-logical-ports-bound-to-physical-ports"></a>Mejorar el rendimiento, ya que minimiza el uso de puertos lógicos que se enlaza a los puertos físicos  
 Puede aumentar el rendimiento, ya que minimiza el uso de puertos lógicos que se enlaza a los puertos físicos que utilizan los siguientes adaptadores:  
  
- SQL Server, Oracle  
  
- WSE, HTTP, WCF  
  
- MSMQ, MQSeries  
  
  En BizTalk Server 2010, enviar y recibir las canalizaciones se pueden invocar directamente desde una orquestación mediante la clase XLANGPipelineManager contenida en el Microsoft.XLANGs.Pipeline.dll. Por lo tanto, se puede mover el procesamiento de canalizaciones de puertos en orquestaciones; puertos lógicos de una orquestación pueden sustituirse con una forma de expresión, que llama a una instancia de una clase determinada de .NET (por ejemplo, un componente de acceso a datos mediante ADO.NET). Antes de adoptar esta técnica, debe tener en cuenta que si no utiliza adaptadores y puertos físicos, perder la capacidad de aprovechar sus funciones, como el procesamiento por lotes, reintentos, configuración declarativa y transportes secundarios.  
  
## <a name="orchestration-design-patterns"></a>Patrones de diseño de orquestación  
 El Diseñador de orquestaciones permite a los desarrolladores implementar una amplia variedad de patrones de integración empresarial. Algunos modelos comunes incluyen el agregador, control de excepciones y compensación, agente de mensajes, dispersión y recopilación y secuencial y Convoy paralelo. Estos patrones se pueden usar para desarrollar soluciones complejas de administración de procesos empresariales (BPM), la arquitectura orientada a servicios (SOA) y Enterprise Application Integration (EAI) con BizTalk Server. Para obtener más información sobre los patrones de diseño de orquestación, vea el tema [implementar patrones de diseño de orquestaciones](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) en la documentación de BizTalk Server y [patrones y procedimientos recomendados para Enterprise Integration Pack](http://go.microsoft.com/fwlink/?LinkId=140043) (http://go.microsoft.com/fwlink/?LinkId=140043).  
  
## <a name="make-appropriate-use-of-net-classes-in-orchestrations-to-maximize-performance"></a>Hacer un uso adecuado de clases de .NET en orquestaciones para maximizar el rendimiento  
 En general, las clases de .NET que se usa dentro de una orquestación pueden dividirse en dos categorías distintas:  
  
-   **Las aplicaciones auxiliares y servicios -** estas clases proporcionan servicios comunes a las orquestaciones, como el seguimiento, control de errores, almacenamiento en caché y serialización y deserialización. La mayoría de estas clases se puede implementar como clases estáticas con ningún estado interno y varios métodos estáticos públicos. Este enfoque evita la creación de varios objetos de la misma clase en orquestaciones diferentes que se ejecutan al mismo tiempo, lo que ayuda a reducir el espacio de trabajo de procesos de host y ahorrar memoria. Una clase que no tiene estada ayuda a reducir el tamaño total del estado interno que se debe serializar y almacena BizTalk MessageBox cuando una orquestación se deshidratará.  
  
-   **Las entidades y objetos de negocios -** puede utilizar estas clases para administrar entidades, como pedidos, elementos pedidos y clientes. Internamente, una orquestación única puede crear y administrar varias instancias del mismo tipo. Estas clases son normalmente con estado y exponen campos públicos o propiedades junto con los métodos para modificar el estado interno del objeto. Instancias de estas clases se pueden crear dinámicamente mediante la deserialización de una parte de XLANGMessage en un objeto .NET mediante el uso de la **XmlSerializer** o **DataContractSerializer** clases o bien utilizando el  **XLANGPart.RetrieveAs** método. Debe estructurar una orquestación mediante ámbitos no transaccionales de tal manera que las instancias de clases con estado se crean en tiempo de ejecución como sea posible y se liberan en cuanto ya no son necesarios. Este enfoque reduce el espacio de trabajo de procesos de host y minimiza el tamaño total del estado interno que se serializa y se conservan en la base de datos de cuadro de mensajes cuando se deshidrata una orquestación. Para obtener más información acerca de cómo utilizar orquestaciones de BizTalk Server, consulte el artículo [preguntas más frecuentes sobre las orquestaciones de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=116886) (http://go.microsoft.com/fwlink/?LinkID=116886).  
  
    > [!NOTE]  
    >  Aunque este artículo se escribió para BizTalk Server 2004 y BizTalk Server 2006, los conceptos presentados también se aplican a las orquestaciones de BizTalk Server 2010.  
  
## <a name="orchestration-exception-handler-blocks"></a>Bloques de controlador de excepciones de orquestación  
 Al utilizar bloques de controlador de excepciones de orquestación, incluir todas las formas de orquestación en uno o varios ámbitos (ámbitos no transaccionales siempre que sea posible) y cree al menos los siguientes bloques de controlador de excepción:  
  
- Un bloque de controlador de excepción para controlar un error genérico de System.Exception.  
  
- Un bloque de controlador de excepción para controlar una excepción general con el fin de detectar y controlar los posibles errores de no administrados, como las excepciones de COM.  
  
  Para obtener más información sobre el uso de bloques de control de excepciones de orquestación, consulte los artículos siguientes:  
  
- [Mediante el control de excepciones de BizTalk Server](http://msdn.microsoft.com/library/aa561229.aspx) (http://msdn.microsoft.com/library/aa561229.aspx).  
  
- [Blog de Young Charles, BizTalk Server 2006: El modelo de compensación](http://go.microsoft.com/fwlink/?LinkId=158017) (http://go.microsoft.com/fwlink/?LinkId=158017).  
  
  > [!NOTE]
  >  Aunque esta entrada de blog se ha redactado teniendo [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] en mente, los principios descritos en el blog también se aplican a BizTalk Server.  
  
## <a name="considerations-when-using-maps-in-orchestrations"></a>Consideraciones al usar asignaciones en orquestaciones  
 Las siguientes consideraciones se aplican al uso de asignaciones en orquestaciones:  
  
-   Si está usando una asignación para extraer o establecer las propiedades usadas con lógica de negocios en una orquestación, utilice los campos distintivos o propiedades promocionadas. Se debe seguir esta práctica porque al extraer o establecer valores con un mapa del documento se carga en memoria pero al usar campos distintivos o propiedades promocionadas, el motor de orquestaciones obtiene acceso al contexto de mensaje y no se carga el documento en la memoria.  
  
-   Si utiliza una asignación para agregar varios campos a un campo, use campos distintivos o propiedades promocionadas con una variable de orquestación para acumular el conjunto de resultados.  
  
## <a name="see-also"></a>Vea también  
 [Optimización del rendimiento](../technical-guides/optimizing-performance.md)