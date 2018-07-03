---
title: Definir procesos empresariales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5e0fdfe-e298-4f32-a7c5-d081b926a206
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50d4d884f60e53fbad465d2b22948a6df6b69256
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002213"
---
# <a name="defining-business-processes"></a>Definir procesos empresariales
El intercambio de mensajes entre distintos sistemas es un trámite necesario para resolver los problemas a los que se enfrenta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Sin embargo, el verdadero objetivo consiste en definir y ejecutar los procesos empresariales basados en las aplicaciones. El motor de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa orquestaciones para definir la lógica de estos procesos empresariales. Para crear y evaluar grupos de reglas de negocios, se utiliza el motor de reglas de negocios. En esta sección se describen las orquestaciones y el motor de reglas de negocios.  
  
## <a name="using-orchestrations"></a>Utilizar orquestaciones  
 La lógica de un proceso empresarial automatizado puede implementarse directamente en un lenguaje como, por ejemplo, Microsoft Visual Basic o Microsoft Visual C#. Sin embargo, la creación, el mantenimiento y la administración de procesos empresariales complejos en lenguajes de programación convencionales pueden resultar todo un reto. A diferencia de sus predecesores, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adopta un enfoque diferente. Permite a los gestores empresariales o programadores definir un proceso empresarial de forma gráfica. Este método puede ser más rápido que la creación del proceso directamente en un lenguaje de programación y, además, puede hacer que el proceso sea más fácil de comprender, explicar y cambiar. También es más fácil supervisar los procesos empresariales que se crean de esta forma, función desarrollada por la tecnología de Supervisión de la actividad económica (SAE).  
  
 Para un desarrollador, creación de una orquestación se basa en tres herramientas principales: el Editor de BizTalk para crear esquemas XML, el asignador de BizTalk para definir las traducciones entre dichos esquemas y el Diseñador de orquestaciones para especificar la lógica de negocios procesos. Todas estas herramientas están alojadas en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], con lo que se proporciona a los programadores un entorno uniforme. En esta sección se describe cada una de estas herramientas y el modo de funcionamiento conjunto.  
  
### <a name="creating-schemas-the-biztalk-editor"></a>Creación de esquemas: El Editor de BizTalk  
 Las orquestaciones funcionan con documentos XML, cada uno de los cuales se ajusta a algún esquema XML. El Editor de BizTalk permite a los programadores definir estos esquemas, que establecen de una forma básica la estructura y los tipos de información de un documento mediante el lenguaje de Definición de esquemas XML (XSD).  
  
 La creación de esquemas XSD sin formato sin utilizar ninguna herramienta no es tarea sencilla. Para facilitar este paso, el Editor de BizTalk permite a los usuarios, posiblemente a los programadores, crear un esquema mediante la definición de sus elementos en una jerarquía gráfica. También podrá importar los esquemas existentes desde archivos o servicios Web a los que pueda obtener acceso. Independientemente de la forma en la que se obtengan, los esquemas se utilizan como base para las asignaciones de BizTalk.  
  
### <a name="mapping-between-schemas-the-biztalk-mapper"></a>Asignación entre esquemas: El asignador de BizTalk  
 Una orquestación que implementa un proceso empresarial normalmente recibe algunos documentos y envía otros. Con frecuencia, parte de la información que contienen los documentos recibidos suele transferirse a los documentos enviados, puede que modificada de algún modo. Por ejemplo, el procesamiento de un pedido puede recibir un pedido de un número de elementos y, a continuación, enviar un mensaje para indicar que el pedido se ha rechazado por alguna razón. La información sobre el pedido, como el identificador de solicitud y la cantidad solicitada, puede copiarse de los campos del mensaje de pedido recibido en los campos del mensaje de rechazo. Puede utilizar el Asignador de BizTalk para definir una transformación, lo que se denomina una asignación, de un documento a otro.  
  
 ![Asignar entre esquemas](../core/media/understandingbts-2010-mapper.gif "UnderstandingBTS_2010_Mapper")  
  
 Como muestra la ilustración anterior, cada asignación se expresa como una correlación gráfica entre dos esquemas XML que define una relación entre los elementos de dichos esquemas. El Worldwide Web Consortium (W3C) ha definido la transformación del lenguaje XSL (XSLT) como el modo estándar para expresar este tipo de transformaciones entre esquemas XML. Por ello, las asignaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se implementan como transformaciones XSLT.  
  
 La transformación definida en una asignación puede ser simple, como, por ejemplo, la copia de valores sin modificar de un documento a otro. La copia directa de datos, como la anterior, se expresa por medio de un vínculo, que aparece en el Asignador de BizTalk como una línea que conecta los elementos apropiados del esquema de origen con los elementos correspondientes del esquema de destino. También se pueden especificar transformaciones más complejas mediante la utilización de functoids. Un functoid consiste en un fragmento de código ejecutable que puede definir asignaciones complejas arbitrarias entre esquemas XML. Como se indica anteriormente, está representado en el Asignador de BizTalk mediante un cuadro situado en la línea que conecta los elementos que se transforman. Ya que algunas de esas transformaciones son bastante comunes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye un número de functoids integrados. Estos functoids integrados se agrupan en categorías, entre las que se incluyen las siguientes:  
  
- Functoids matemáticos que llevan a cabo operaciones de suma, multiplicación y división de valores de campos del documento de origen y almacenan el resultado en un campo del documento de destino.  
  
- Functoids de conversión que transforman un valor numérico en el equivalente de ASCII y viceversa.  
  
- Functoids lógicos que se utilizan para determinar si un elemento o atributo debería crearse en el documento de destino basándose en una comparación lógica entre valores especificados en el documento de origen. Estos valores pueden compararse en términos de igualdad y de relación mayor o menor que, entre otros.  
  
- Functoids acumulados que calculan los promedios, sumas u otros valores de distintos campos del documento de origen y, a continuación, almacenan el resultado en un mismo campo del documento de destino.  
  
- Functoids de bases de datos que pueden obtener acceso a la información almacenada en una base de datos.  
  
  También puede crear functoids personalizados directamente en XSLT o mediante lenguajes compatibles con .NET, como, por ejemplo, Visual C#  y Visual Basic Los functoids también pueden combinarse en secuencias, intercalando la salida de uno con la entrada de otro.  
  
  Resulta esencial disponer de un modo para definir el esquema XML de un documento y asignar la información de documentos con distintos esquemas. El Editor de BizTalk y el Asignador de BizTalk hacen frente a estos dos problemas. No obstante, la definición de esquemas y asignaciones sólo representa una parte del proceso. También debe especificar la lógica de negocios que utilizará los esquemas e invocará las asignaciones.  
  
### <a name="defining-business-logic-the-orchestration-designer"></a>Definir lógica de negocios: El Diseñador de orquestaciones  
 Un proceso empresarial es un conjunto de acciones que satisfacen de forma conjunta ciertas necesidades empresariales útiles. Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], un desarrollador puede usar el diseñador de orquestaciones para definir estas acciones gráficamente. En lugar de expresar los pasos en un lenguaje de programación determinado, esta herramienta permitirá a los programadores crear una orquestación mediante la conexión lógica de una serie de formas. Entre las formas disponibles en el Diseñador de orquestaciones se incluyen:  
  
- La forma Recepción, que permite a la orquestación recibir mensajes. La forma Recepción puede disponer de un filtro que defina qué tipos de mensajes se recibirán; además, se puede configurar para que inicie una nueva instancia de orquestación cuando llegue un mensaje nuevo.  
  
- La forma Envío, que permite a la orquestación enviar mensajes.  
  
- La forma Puerto, que define cómo se transmiten los mensajes. Cada instancia de una forma Puerto se conecta a una forma Envío o Recepción. Asimismo, cada puerto posee un tipo, que define aspectos como los tipos de mensaje que el puerto puede recibir; una dirección, como, por ejemplo, envío o recepción; y un enlace, que determina el medio por el que se envía o se recibe un mensaje, por ejemplo, la especificación de una dirección URL determinada y otro tipo de información.  
  
- La forma Decidir, que representa una instrucción if-then-else que permite que una orquestación realice diferentes tareas basadas en condiciones booleanas. Puede utilizar un Editor de expresiones, componente del Diseñador de orquestaciones, para especificar esta instrucción condicional.  
  
- La forma Bucle, que controla las repeticiones de una acción cuando una condición está definida como True.  
  
- La forma Construir, que permite la generación de un mensaje.  
  
- La forma Transformación, que permite transferir información entre documentos y transformarla mediante la invocación de asignaciones definidas con el Asignador de BizTalk.  
  
- La forma Acciones paralelas, que permite a un programador especificar que varias operaciones deben realizarse en paralelo en lugar de en una sola secuencia. La forma posterior a ésta no se ejecuta hasta que se han completado todas las acciones paralelas.  
  
- La forma Ámbito, que permite agrupar operaciones en transacciones y definir los controladores de excepción para el control de errores. El sistema admite tanto las transacciones atómicas como las de larga ejecución. Al contrario que las transacciones atómicas, las transacciones de larga ejecución están basadas en una lógica de compensación, en lugar de revertir la acción para controlar los sucesos inesperados.  
  
- La forma Asignación de mensajes, que permite asignar valores a las variables de orquestación. Estas variables se pueden utilizar para almacenar información de estado de la orquestación, como, por ejemplo, un mensaje que se esté creando o una cadena de caracteres.  
  
  En la siguiente ilustración se muestra una orquestación creada por el Diseñador de orquestaciones con algunas de estas formas. En este ejemplo sencillo, se recibe un mensaje, se toma una decisión en función del contenido de dicho mensaje y se ejecuta una de las dos rutas posibles como resultado de esa decisión. Las orquestaciones que resuelven problemas reales pueden resultar significativamente más complejas que ésta. Para facilitar el trabajo con estos diagramas más complejos, el Diseñador de orquestaciones incluye la capacidad de acercar y alejar. De esta forma, los programadores sólo verán aquellas partes de la orquestación que les interesen.  
  
  ![](../core/media/understandingbts-08-orchestration.gif "UnderstandingBTS_08_Orchestration")  
  
  Una vez que un programador ha definido una orquestación, el grupo de formas y relaciones entre ellas se convierte en Lenguaje intermedio de Microsoft (MSIL) utilizado por el Common Language Runtime (CLR) de .NET Framework. Por último, el grupo de formas definidas por un programador de BizTalk Server pasa a ser el ensamblado estándar compatible con .NET. También es posible agregar código explícito a una orquestación cuando sea necesario; para ello, se llama a un objeto COM o .NET desde el interior de una forma.  
  
### <a name="the-role-of-web-services"></a>La función de los servicios Web  
 Los servicios Web permiten a las aplicaciones intercambiar documentos XML mediante SOAP y han tenido un impacto significativo en las plataformas de integración. Para obtener acceso a un servicio Web externo, el creador de una orquestación puede usar la opción Agregar referencia Web en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] junto con el adaptador de servicios Web para invocar operaciones directamente. De forma similar, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona un Asistente para publicación de servicios Web, que puede generar un proyecto de servicio Web ASP.NET que exponga una o varias de las operaciones de una orquestación como servicios Web a los que se pueda llamar mediante SOAP. Estas dos opciones permiten a los programadores obtener acceso a los servicios Web existentes desde un proceso empresarial y exponer la funcionalidad de una orquestación como un servicio Web a otros procesos empresariales.  
  
- El auge de los servicios Web también afecta a cómo se definen los procesos empresariales. Suponga, por ejemplo, que dos organizaciones interactúan mediante servicios Web. Para que puedan trabajar conjuntamente de forma efectiva, puede que cada parte de la interacción necesite saber cierta información sobre el proceso empresarial que utiliza el otro. Que ambas organizaciones usen [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no supone un gran problema; pueden emplearse herramientas como la tecnología de Administración de socios comerciales para distribuir esta información. Sin embargo, ¿qué ocurre si utilizan productos diferentes? En este caso resulta de utilidad disponer de una forma para describir ciertos aspectos de los procesos empresariales desde el punto de vista de una persona que no es fabricante.  
  
  Para permitir este tipo de interacción, Microsoft, IBM y otras empresas han creado el lenguaje de ejecución de procesos empresariales (BPEL). Un proceso empresarial definido mediante el Diseñador de orquestaciones puede exportarse a BPEL, y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también puede importar procesos definidos en BPEL. Pese a que el lenguaje resulta útil para describir y compartir de forma externa las partes visibles de los procesos empresariales, BPEL se centra más en la resolución de este problema que en la ejecución de procesos empresariales completos en plataformas cruzadas. También es importante el hecho de que BPEL esté basado por completo en servicios Web, mientras que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y otros productos compatibles con este lenguaje proporcionan mucho más. Por ejemplo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite la asignación entre distintos esquemas XML, métodos de llamada en objetos locales y otras características no disponibles en BPEL. Por éstas y otras razones, BPEL no se considera un lenguaje completo para la definición de procesos empresariales. Además, dado que BPEL aún se encuentra en proceso para recibir la denominación de estándar del sector de OASIS (del inglés, Organization for the Advancement of Structured Information Standards), resulta complicado verlo hoy en día como una tecnología consolidada por completo.  
  
- Las orquestaciones constituyen el mecanismo fundamental para la creación de procesos empresariales en BizTalk Server. Sin embargo, algunos aspectos de la orquestación suelen cambiar más a menudo que otros. En concreto, las decisiones integradas en un proceso empresarial, las reglas de negocios, representan por lo general su aspecto más volátil. Límite de gasto de un administrador fuera de 100.000 dólares última semana, pero su moroso esto hasta 500.000 dólares o disminuye la máxima permitida de pedido del cliente descienda de 100 unidades a 10 únicamente. Puede especificar y actualizar estas reglas mediante el motor de reglas de negocios.  
  
## <a name="using-the-business-rule-engine"></a>Utilizar el motor de reglas de negocios  
 El Diseñador de orquestaciones, junto con el Editor de BizTalk y el Asignador de BizTalk, proporcionan un modo eficaz de definir un proceso empresarial y las reglas que utiliza. No obstante, puede resultar útil contar con una forma más sencilla de definir y cambiar estas reglas de negocios. Para permitirlo, BizTalk Server ofrece el motor de reglas de negocios (BRE). Los programadores serán los que utilicen el BRE con mayor frecuencia, pero, por otra parte, los usuarios más orientados al sector empresarial pueden crear y modificar conjuntos de reglas de negocios con una herramienta denominada Compositor de reglas de negocio.  
  
 Una situación en la que el BRE resulta de utilidad es cuando se debe evaluar un conjunto complejo de reglas de negocios. La decisión de conceder un préstamo, por ejemplo, puede implicar trabajar a través de un conjunto grande de reglas en función del historial crediticio del cliente, sus ingresos y otros factores. De la misma forma, la concesión de un seguro de vida a un solicitante depende de un número de factores, entre los que se incluyen la edad, el sexo y estado de salud del solicitante. La expresión de todas estas reglas como instrucciones condicionales podría realizarse por medio de una forma Decidir de una orquestación, pero también puede resultar demasiado complejo implementarlas. En aquellos procesos en los que se empleen muchas reglas, como es el caso, el BRE puede facilitar el trabajo al programador.  
  
 Gracias al BRE, los programadores pueden cambiar las reglas cuando lo necesiten de una forma rápida y sencilla. Para entenderlo, piense en lo que se necesita para cambiar una regla de negocios que se implementa en una orquestación. En primer lugar, el programador debe abrir la orquestación en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], modificar las formas adecuadas (y quizás los objetos .NET o COM que invocan) y, a continuación, crear e implementar el ensamblado modificado. Este proceso también exige la detención y el reinicio de la aplicación de BizTalk que incluye esta orquestación. Si, en lugar de ello, esta regla de negocios se implementa con el BRE, se puede modificar sin volver a compilar ni reiniciar nada. Sólo necesitará utilizar el Compositor de reglas de negocio para cambiar la regla deseada y volver a implementar el nuevo conjunto de reglas. El cambio surtirá efecto de inmediato. Aunque son los programadores quienes suelen crear y mantener las orquestaciones, las reglas de negocios son lo suficientemente comprensibles para que los analistas de negocios las puedan modificar en algunas ocasiones sin necesidad de implicar a ningún técnico.  
  
 El creador de un conjunto de reglas de negocios normalmente comienza con el Compositor de reglas de negocio para definir un vocabulario que especifique las reglas. Cada término del vocabulario proporciona un nombre sencillo para algún tipo de información. Por ejemplo, en un vocabulario se pueden definir términos como número enviado, cantidad máxima de elementos o límite de aprobación. Cada uno de estos términos puede establecerse en una constante o asignarse a un atributo o elemento determinado en algún esquema XML (y, de esta forma, en un mensaje entrante), al resultado de una consulta SQL realizada en una base de datos o a un valor de un objeto .NET.  
  
 Una vez que se ha definido un vocabulario, se puede utilizar el Compositor de reglas de negocio para crear directivas empresariales que empleen dicho vocabulario. Cada directiva puede contener una o varias reglas de negocios. Una regla utiliza los términos definidos en un vocabulario, así como operadores lógicos del tipo Mayor que, Menor que, Igual a, etc., con el objetivo de definir el funcionamiento de un proceso empresarial. Una regla de negocios puede definir, entre otros aspectos, cómo deberían afectar los valores de un documento XML recibido a los valores creados en un documento XML que se envía, o cómo deberían afectar esos valores recibidos a un valor determinado escrito en una base de datos.  
  
 Para ejecutar una directiva empresarial, las orquestaciones utilizan la forma CallRules. Esta forma crea una instancia del BRE, especifica la directiva que se va a ejecutar y entra en la información que la directiva necesita, como, por ejemplo, en un documento XML recibido. También puede invocarse el BRE mediante programación por medio de un modelo de objetos basado en .NET, que permite llamarlo desde aplicaciones que no usan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esto implica que tanto aplicaciones de Windows Forms, como servicios Web de exposición de software y cualquier elemento que se haya generado en .NET Framework podrían utilizar el BRE cuando ayude a resolver el problema al que se enfrentan.  
  
 Los vocabularios y las reglas de negocios pueden resultar más complicadas (y mucho más eficaces) que los sencillos ejemplos que se describen en esta sección. No obstante, la idea principal de definir un vocabulario y, posteriormente, los conjuntos de reglas que lo utilizan, es la esencia del motor de reglas de negocios.  
  
## <a name="see-also"></a>Vea también  
 [El motor de mensajería de BizTalk Server](../core/the-biztalk-server-messaging-engine.md)