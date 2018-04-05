---
title: Lenguaje XLANG s | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, properties
ms.assetid: 97b62f17-5a8d-4d87-8563-1f6d941f027f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2329d4bc42617d70227481a0d70064d368f3c0e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-language"></a>Lenguaje XLANG-s.
XLANG/s se diseñó para usar estándares de Internet como XML, XSD y Lenguaje de descripción de servicios Web (WSDL) y dispone de compatibilidad integrada para trabajar con mensajes y objetos basados en .NET. XLANG/s se puede ver como un lenguaje de mensajería con algunas de las capacidades de expresión de C#. Sin embargo, no se puede exportar el código entre XLANG/s y C#.  
  
 XLANG/s recomienda que se realice una separación clara entre el proceso y la implementación. Por ejemplo, el proceso empresarial o protocolo se especifica en XLANG/s y los aspectos locales de la aplicación, como el acceso a las bases de datos, se implementan en otros lenguajes de programación de .NET como C# o Visual Basic.NET.  
  
 La sintaxis de expresiones y la asignación de XLANG/s se basan en C#, por lo que debería hacer referencia a la especificación de C# para una sintaxis exacta. XLANG/s define un nutrido conjunto de construcciones de alto nivel que se usan para definir procesos empresariales. Aunque XLANG/s proporciona compatibilidad para los tipos de datos de bajo nivel como cadenas y enteros, también se definen los tipos de datos de alto nivel: mensajes, puertos, correlaciones y vínculos de servicio. Estos tipos de datos se utilizan para definir rigurosamente la semántica asociada a un proceso empresarial y se complementan con el proceso de las instrucciones de control como **mientras** o **ámbito**.  
  
 Instrucciones de XLANG/s suelen pertenecen a una de estas dos categorías: instrucciones sencillas que actúan por sí mismas, como **recibir** o **enviar**y las instrucciones complejas que contienen o agrupan cualquier instrucciones sencillas o otras instrucciones complejas, como **ámbito**, **paralelo**, y **escuchar**. Las semánticas incluidas en XLANG/s son una reflexión de las que se definen en la especificación del lenguaje de ejecución de procesos empresariales para servicios Web (BPEL4WS) publicada por Microsoft, IBM y BEA para la definición de semánticas de procesos empresariales.  
  
 No es necesario comprender las construcciones principales de XLANG/s ya que son el resultado de dibujar diagramas de orquestación en el Diseñador de orquestaciones de BizTalk. El Diseñador de orquestaciones es una completa herramienta gráfica para diseñar visualmente procesos empresariales. Genera archivos XLANG/s con una extensión .odx que contienen información visual adicional en los encabezados e información de atributos personalizados en el cuerpo.  
  
> [!NOTE]
>  El lenguaje XLANG/s es de propietario y no está completamente documentado. En esta sección se explican determinadas partes del lenguaje que es posible que necesite tener en cuenta cuando desarrolle orquestaciones. No se admite la modificación directa de los archivos .odx.  
  
## <a name="xlangs-programs"></a>Programas de XLANG/s  
 El programa más sencillo de XLANG/s necesita que se defina un tipo de mensaje, que dará a la orquestación algunos datos con los que comenzar a trabajar. La orquestación recibe el mensaje a través de un puerto y, a continuación, finaliza. A continuación se muestra un ejemplo de código:  
  
```  
module HelloWorldApp  
{  
     private porttype ptPOReceive  
     {  
      oneway opPOReceive  
      {  
       HelloWorldApp.PurchaseOrder  
      }  
     }  
     private porttype ptPOSend  
     {  
      oneway opPOSend  
      {  
       HelloWorldApp.PurchaseOrder  
      }  
     }  
     private service  HelloWorld  
     {  
      port implements HelloWorldApp.ptPOReceive poPOReceive;  
      port uses HelloWorldApp.ptPOSend poPOSend;  
      message HelloWorldApp.PurchaseOrder msgPO;  
      body ()  
      {  
       activate receive (poPOReceive.opPOReceive, msgPO);  
       send (poPOSend.opPOSend, msgPO);  
       }  
     }  
}  
```  
  
 En el programa XLANG/s anterior, el `module` palabra clave define la unidad de compilaciones para un programa XLANG/s. Todos los tipos utilizados en el programa, como **porttype**, **correlationsettype**, **servicelinktype**, y **messagetype**: se sitúa en Este nivel.  
  
 Un puerto es una construcción que puede enviar o recibir mensajes hacia o desde XLANG/s, y el puerto tiene un tipo definido denominado **porttype**. El **porttype** construcción define una colección de operaciones que se puede usar en el puerto. Estas operaciones definen un único intercambio de mensajes válido a través del puerto. En la definición de **porttype**, **messagetype**, **servicelinktype**, o **correlationsettype** construye, el autor de XLANG/s programa básicamente es crear definiciones de tipos de datos complejos. Estas definiciones tienen las mismas ventajas que tipos de datos complejos en otros lenguajes: resumen las nociones incluidas en el tipo de datos a un nivel superior y permitir para facilitar su reutilización del tipo de datos.  
  
 El **ptPOReceive** operación de puerto de recepción de puerto en el módulo se define con un unidireccional de HelloWorldApp anterior **opPOReceive**. El bloque HelloWorld de servicio define la implementación real del proceso y cualquier variable que pueda usar, incluidas las variables de puertos y de mensajes. Las tres primeras líneas de código dentro de este bloque definen las variables de puerto **poPOReceive** y **poPOSend** y el mensaje **msgPO** respectivamente. El cuerpo contiene el código que describe parámetros al servicio y al comportamiento de ejecución. Todas las variables, excepto que estén definidas con un bloque de ámbito anidado, pertenecen al ámbito de este nivel. La instrucción receive, que es una recepción de activación, recibe el **msgPO** mensaje desde el **poPOReceive.opPOReceive** puerto y crea una nueva instancia de la orquestación. Una vez recibido el mensaje, la instrucción de envío dirige el mensaje a un puerto de envío. En las declaraciones de dos puertos en el código anterior, **poPOReceive** usa el modificador de implementaciones, mientras que **poPOSend** utiliza el modificador de usos. El modificador de implementaciones indica el tiempo de ejecución que tardará en recibirse un mensaje a través de ese puerto. El modificador de usos indica el tiempo de ejecución que tardará en enviarse un mensaje a través de ese puerto.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Tipos de datos de XLANG-s](../core/xlang-s-data-types.md)  
  
-   [Instrucciones de XLANG-s](../core/xlang-s-statements.md)  
  
-   [Operadores y Variables de XLANG-s](../core/xlang-s-variables-and-operators.md)  
  
-   [Expresiones de XLANG-s](../core/xlang-s-expressions.md)  
  
-   [Palabras reservadas de XLANG-s](../core/xlang-s-reserved-words.md)  
  
-   [XLANG-s para las conversiones de tipo de BPEL4WS](../core/xlang-s-to-bpel4ws-type-conversions.md)  
  
## <a name="see-also"></a>Vea también  
 [Acerca del motor de orquestación de BizTalk](../core/about-the-biztalk-orchestration-engine.md)