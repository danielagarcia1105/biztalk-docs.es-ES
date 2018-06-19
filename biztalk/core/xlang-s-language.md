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
ms.locfileid: "22290916"
---
# <a name="xlang-s-language"></a><span data-ttu-id="e348b-102">Lenguaje XLANG-s.</span><span class="sxs-lookup"><span data-stu-id="e348b-102">XLANG-s Language</span></span>
<span data-ttu-id="e348b-103">XLANG/s se diseñó para usar estándares de Internet como XML, XSD y Lenguaje de descripción de servicios Web (WSDL) y dispone de compatibilidad integrada para trabajar con mensajes y objetos basados en .NET.</span><span class="sxs-lookup"><span data-stu-id="e348b-103">XLANG/s was designed to use Internet standards such as XML, XSD, and Web Services Description Language (WSDL), and has embedded support for working with .NET-based objects and messages.</span></span> <span data-ttu-id="e348b-104">XLANG/s se puede ver como un lenguaje de mensajería con algunas de las capacidades de expresión de C#.</span><span class="sxs-lookup"><span data-stu-id="e348b-104">XLANG/s can be viewed as a messaging language with some of the expression capabilities of C#.</span></span> <span data-ttu-id="e348b-105">Sin embargo, no se puede exportar el código entre XLANG/s y C#.</span><span class="sxs-lookup"><span data-stu-id="e348b-105">However, code is not portable between XLANG/s and C#.</span></span>  
  
 <span data-ttu-id="e348b-106">XLANG/s recomienda que se realice una separación clara entre el proceso y la implementación.</span><span class="sxs-lookup"><span data-stu-id="e348b-106">XLANG/s encourages a clear separation between process and implementation.</span></span> <span data-ttu-id="e348b-107">Por ejemplo, el proceso empresarial o protocolo se especifica en XLANG/s y los aspectos locales de la aplicación, como el acceso a las bases de datos, se implementan en otros lenguajes de programación de .NET como C# o Visual Basic.NET.</span><span class="sxs-lookup"><span data-stu-id="e348b-107">For example, the business process or protocol is specified in XLANG/s, and the local aspects of the application, such as database access, are implemented in other .NET programming languages such as C# or Visual Basic.NET.</span></span>  
  
 <span data-ttu-id="e348b-108">La sintaxis de expresiones y la asignación de XLANG/s se basan en C#, por lo que debería hacer referencia a la especificación de C# para una sintaxis exacta.</span><span class="sxs-lookup"><span data-stu-id="e348b-108">XLANG/s assignment and expression syntax is modeled after C#, and you should reference the C# specification for exact syntax.</span></span> <span data-ttu-id="e348b-109">XLANG/s define un nutrido conjunto de construcciones de alto nivel que se usan para definir procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="e348b-109">XLANG/s defines a rich set of high-level constructs that are used to define business processes.</span></span> <span data-ttu-id="e348b-110">Aunque XLANG/s proporciona compatibilidad para los tipos de datos de bajo nivel como cadenas y enteros, también se definen los tipos de datos de alto nivel: mensajes, puertos, correlaciones y vínculos de servicio.</span><span class="sxs-lookup"><span data-stu-id="e348b-110">While XLANG/s provides support for low-level data types like string and integer, high-level data types are also defined: messages, ports, correlations, and service links.</span></span> <span data-ttu-id="e348b-111">Estos tipos de datos se utilizan para definir rigurosamente la semántica asociada a un proceso empresarial y se complementan con el proceso de las instrucciones de control como **mientras** o **ámbito**.</span><span class="sxs-lookup"><span data-stu-id="e348b-111">These data types are used to rigorously define the semantics associated with a business process, and are complemented by process control statements such as **while** or **scope**.</span></span>  
  
 <span data-ttu-id="e348b-112">Instrucciones de XLANG/s suelen pertenecen a una de estas dos categorías: instrucciones sencillas que actúan por sí mismas, como **recibir** o **enviar**y las instrucciones complejas que contienen o agrupan cualquier instrucciones sencillas o otras instrucciones complejas, como **ámbito**, **paralelo**, y **escuchar**.</span><span class="sxs-lookup"><span data-stu-id="e348b-112">XLANG/s statements generally fall into one of two categories: simple statements that act on their own, such as **receive** or **send**, and complex statements that contain or group either simple statements or other complex statements, such as **scope**, **parallel**, and **listen**.</span></span> <span data-ttu-id="e348b-113">Las semánticas incluidas en XLANG/s son una reflexión de las que se definen en la especificación del lenguaje de ejecución de procesos empresariales para servicios Web (BPEL4WS) publicada por Microsoft, IBM y BEA para la definición de semánticas de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="e348b-113">The semantics embodied in XLANG/s are a reflection of those defined in the Business Process Execution Language for Web Services (BPEL4WS) specification published by Microsoft, IBM, and BEA for the definition of business process semantics.</span></span>  
  
 <span data-ttu-id="e348b-114">No es necesario comprender las construcciones principales de XLANG/s ya que son el resultado de dibujar diagramas de orquestación en el Diseñador de orquestaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e348b-114">Understanding the main constructs of XLANG/s is optional because they are produced as a result of drawing orchestration diagrams in BizTalk Orchestration Designer.</span></span> <span data-ttu-id="e348b-115">El Diseñador de orquestaciones es una completa herramienta gráfica para diseñar visualmente procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="e348b-115">Orchestration Designer is a rich graphical tool for visually designing business processes.</span></span> <span data-ttu-id="e348b-116">Genera archivos XLANG/s con una extensión .odx que contienen información visual adicional en los encabezados e información de atributos personalizados en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="e348b-116">It generates XLANG/s files that have an .odx extension and contain additional visual information in their headers and custom attribute information in their bodies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e348b-117">El lenguaje XLANG/s es de propietario y no está completamente documentado.</span><span class="sxs-lookup"><span data-stu-id="e348b-117">The XLANG/s language is proprietary and is not fully documented.</span></span> <span data-ttu-id="e348b-118">En esta sección se explican determinadas partes del lenguaje que es posible que necesite tener en cuenta cuando desarrolle orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="e348b-118">This section exposes certain parts of the language that you might need to be aware of as you develop your orchestrations.</span></span> <span data-ttu-id="e348b-119">No se admite la modificación directa de los archivos .odx.</span><span class="sxs-lookup"><span data-stu-id="e348b-119">Direct modification of the .odx files is not supported.</span></span>  
  
## <a name="xlangs-programs"></a><span data-ttu-id="e348b-120">Programas de XLANG/s</span><span class="sxs-lookup"><span data-stu-id="e348b-120">XLANG/s Programs</span></span>  
 <span data-ttu-id="e348b-121">El programa más sencillo de XLANG/s necesita que se defina un tipo de mensaje, que dará a la orquestación algunos datos con los que comenzar a trabajar.</span><span class="sxs-lookup"><span data-stu-id="e348b-121">The simplest XLANG/s program requires that a message type be defined, which gives the orchestration some data to start to work with.</span></span> <span data-ttu-id="e348b-122">La orquestación recibe el mensaje a través de un puerto y, a continuación, finaliza.</span><span class="sxs-lookup"><span data-stu-id="e348b-122">The orchestration receives the message over a port and then terminates.</span></span> <span data-ttu-id="e348b-123">A continuación se muestra un ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="e348b-123">The following code is an example:</span></span>  
  
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
  
 <span data-ttu-id="e348b-124">En el programa XLANG/s anterior, el `module` palabra clave define la unidad de compilaciones para un programa XLANG/s.</span><span class="sxs-lookup"><span data-stu-id="e348b-124">In the preceding XLANG/s program, the `module` keyword defines the unit of compilations for an XLANG/s program.</span></span> <span data-ttu-id="e348b-125">Todos los tipos utilizados en el programa, como **porttype**, **correlationsettype**, **servicelinktype**, y **messagetype**: se sitúa en Este nivel.</span><span class="sxs-lookup"><span data-stu-id="e348b-125">All types used in the program—such as **porttype**, **correlationsettype**, **servicelinktype**, and **messagetype**—are scoped at this level.</span></span>  
  
 <span data-ttu-id="e348b-126">Un puerto es una construcción que puede enviar o recibir mensajes hacia o desde XLANG/s, y el puerto tiene un tipo definido denominado **porttype**.</span><span class="sxs-lookup"><span data-stu-id="e348b-126">A port is a construct that XLANG/s can send or receive messages to or from, and the port has a defined type called **porttype**.</span></span> <span data-ttu-id="e348b-127">El **porttype** construcción define una colección de operaciones que se puede usar en el puerto.</span><span class="sxs-lookup"><span data-stu-id="e348b-127">The **porttype** construct defines a collection of operations that can be used on the port.</span></span> <span data-ttu-id="e348b-128">Estas operaciones definen un único intercambio de mensajes válido a través del puerto.</span><span class="sxs-lookup"><span data-stu-id="e348b-128">These operations define a single valid message exchange over the port.</span></span> <span data-ttu-id="e348b-129">En la definición de **porttype**, **messagetype**, **servicelinktype**, o **correlationsettype** construye, el autor de XLANG/s programa básicamente es crear definiciones de tipos de datos complejos.</span><span class="sxs-lookup"><span data-stu-id="e348b-129">In defining **porttype**, **messagetype**, **servicelinktype**, or **correlationsettype** constructs, the author of an XLANG/s program is essentially creating complex data type definitions.</span></span> <span data-ttu-id="e348b-130">Estas definiciones tienen las mismas ventajas que tipos de datos complejos en otros lenguajes: resumen las nociones incluidas en el tipo de datos a un nivel superior y permitir para facilitar su reutilización del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="e348b-130">These definitions have the same advantages as complex data types do in other languages: They abstract the notions embodied in the data type to a higher level, and they allow for easy reuse of the data type.</span></span>  
  
 <span data-ttu-id="e348b-131">El **ptPOReceive** operación de puerto de recepción de puerto en el módulo se define con un unidireccional de HelloWorldApp anterior **opPOReceive**.</span><span class="sxs-lookup"><span data-stu-id="e348b-131">The **ptPOReceive** port in the preceding HelloWorldApp module is defined with a one-way receive port operation, **opPOReceive**.</span></span> <span data-ttu-id="e348b-132">El bloque HelloWorld de servicio define la implementación real del proceso y cualquier variable que pueda usar, incluidas las variables de puertos y de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e348b-132">The service HelloWorld block defines the actual implementation of the process and any variables it may use, including port and message variables.</span></span> <span data-ttu-id="e348b-133">Las tres primeras líneas de código dentro de este bloque definen las variables de puerto **poPOReceive** y **poPOSend** y el mensaje **msgPO** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e348b-133">The first three lines of code within this block define the port variables **poPOReceive** and **poPOSend** and the message **msgPO** respectively.</span></span> <span data-ttu-id="e348b-134">El cuerpo contiene el código que describe parámetros al servicio y al comportamiento de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e348b-134">The body contains the code describing parameters to the service and the execution behavior.</span></span> <span data-ttu-id="e348b-135">Todas las variables, excepto que estén definidas con un bloque de ámbito anidado, pertenecen al ámbito de este nivel.</span><span class="sxs-lookup"><span data-stu-id="e348b-135">All variables, unless defined with a nested scope block, are scoped to this level.</span></span> <span data-ttu-id="e348b-136">La instrucción receive, que es una recepción de activación, recibe el **msgPO** mensaje desde el **poPOReceive.opPOReceive** puerto y crea una nueva instancia de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="e348b-136">The receive statement, which is an activate receive, receives the **msgPO** message from the **poPOReceive.opPOReceive** port and creates a new instance of the orchestration.</span></span> <span data-ttu-id="e348b-137">Una vez recibido el mensaje, la instrucción de envío dirige el mensaje a un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="e348b-137">After the message is received, the send statement directs the message to a send port.</span></span> <span data-ttu-id="e348b-138">En las declaraciones de dos puertos en el código anterior, **poPOReceive** usa el modificador de implementaciones, mientras que **poPOSend** utiliza el modificador de usos.</span><span class="sxs-lookup"><span data-stu-id="e348b-138">In the two port declarations in the preceding code, **poPOReceive** uses the implements modifier, whereas **poPOSend** uses the uses modifier.</span></span> <span data-ttu-id="e348b-139">El modificador de implementaciones indica el tiempo de ejecución que tardará en recibirse un mensaje a través de ese puerto.</span><span class="sxs-lookup"><span data-stu-id="e348b-139">The implements modifier tells the runtime it will be receiving a message over that port.</span></span> <span data-ttu-id="e348b-140">El modificador de usos indica el tiempo de ejecución que tardará en enviarse un mensaje a través de ese puerto.</span><span class="sxs-lookup"><span data-stu-id="e348b-140">The uses modifier tells the runtime that it will be sending a message over that port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e348b-141">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e348b-141">In This Section</span></span>  
  
-   [<span data-ttu-id="e348b-142">Tipos de datos de XLANG-s</span><span class="sxs-lookup"><span data-stu-id="e348b-142">XLANG-s Data Types</span></span>](../core/xlang-s-data-types.md)  
  
-   [<span data-ttu-id="e348b-143">Instrucciones de XLANG-s</span><span class="sxs-lookup"><span data-stu-id="e348b-143">XLANG-s Statements</span></span>](../core/xlang-s-statements.md)  
  
-   [<span data-ttu-id="e348b-144">Operadores y Variables de XLANG-s</span><span class="sxs-lookup"><span data-stu-id="e348b-144">XLANG-s Variables and Operators</span></span>](../core/xlang-s-variables-and-operators.md)  
  
-   [<span data-ttu-id="e348b-145">Expresiones de XLANG-s</span><span class="sxs-lookup"><span data-stu-id="e348b-145">XLANG-s Expressions</span></span>](../core/xlang-s-expressions.md)  
  
-   [<span data-ttu-id="e348b-146">Palabras reservadas de XLANG-s</span><span class="sxs-lookup"><span data-stu-id="e348b-146">XLANG-s Reserved Words</span></span>](../core/xlang-s-reserved-words.md)  
  
-   [<span data-ttu-id="e348b-147">XLANG-s para las conversiones de tipo de BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="e348b-147">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)  
  
## <a name="see-also"></a><span data-ttu-id="e348b-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="e348b-148">See Also</span></span>  
 [<span data-ttu-id="e348b-149">Acerca del motor de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e348b-149">About the BizTalk Orchestration Engine</span></span>](../core/about-the-biztalk-orchestration-engine.md)