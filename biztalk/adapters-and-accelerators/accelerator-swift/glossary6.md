---
title: Glosario de Acelerador de SWIFT en BizTalk Server | Documentos de Microsoft
description: "Común de términos y definiciones para conocer y aprender a usar el Acelerador de BizTalk para SWIFT"
ms.custom: 
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7331beb-f6a7-4eea-8b31-28f5d15666d0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1230b6b1578a4a3aa7c719df4dffb718b0c748e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="glossary"></a>Glosario
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para SWIFT usa las siguientes Glosario de términos y definiciones.  
  
## <a name="a"></a>Un  
 **ensamblador**  
 A [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] componente de canalización de envío que se invoca durante la fase de ensamblado de procesamiento de canalización de salida. Por lo general, un ensamblador realiza el trabajo de serializar un mensaje saliente de XML en algún formato de archivo sin formato.  
  
 **ensamblado**  
 El principal bloque de creación de un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)] aplicación. Es la unidad básica de reutilización, control de versiones, seguridad e implementación. Es una colección de archivos que aparecen para el programador de una biblioteca de vínculo único dinámicos (DLL) o ejecutable (EXE).  
  
 **caché de ensamblados**  
 Caché de código de todo el equipo utilizada para el almacenamiento en paralelo de los ensamblados. Hay dos partes en la memoria caché. La caché de ensamblados global contiene ensamblados que se instalan explícitamente para compartirse entre varias aplicaciones en el equipo. La caché de descarga almacena código descargado de Internet o sitios de la intranet, aislados a la aplicación que desencadena la descarga para que el código descargado en nombre de una aplicación o página no afecta a otras aplicaciones.  
  
## <a name="b"></a>B  
 **Código identificador del banco (BIC)**  
 Un código que se utiliza para identificar una institución financiera, tal como se define por SWIFT.  
  
 **Herramienta de Compositor de reglas de negocios**  
 Herramienta gráfica de interfaz de usuario utilizada para componer directivas.  
  
 **Motor de reglas de negocios (BRE)**  
 Motor de inferencia de tiempo de ejecución que evalúa reglas con respecto a eventos e inicia acciones en función de los resultados de tal evaluación.  
  
## <a name="c"></a>C  
 **regla condicional**  
 Una regla especifica una relación entre los campos de un tipo de mensaje SWIFT. Reglas condicionales se definen en la Guía de la versión de SWIFT estándares.  
  
## <a name="d"></a>D  
 **Desensamblador**  
 Un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] componente de canalización que se invoca durante la fase de desensamblado de procesamiento de la entrada de canalización de recepción. Por lo general, un desensamblador realiza el trabajo de análisis de un mensaje entrante procedente de algún formato de archivo sin formato en XML.  
  
## <a name="e"></a>E  
 **código de error**  
 Código formada por una letra seguida de dos dígitos, que indica una infracción de las reglas para un tipo de mensaje dado determinada.  
  
 **Lenguaje de marcado extensible (XML)**  
 Especificación desarrollada por World Wide Web Consortium (W3C) que permite a los diseñadores crear etiquetas personalizadas más allá de las capacidades de HTML estándar. Mientras que HTML usa solo las etiquetas predefinidas para describir los elementos dentro de la página, XML permite etiquetas sea definido por el desarrollador de la página. Las etiquetas para prácticamente cualquier elemento de datos, como un producto o una cantidad debida, pueden utilizarse para aplicaciones específicas. Esto permite que las páginas web funcionen como registros de la base de datos.  
  
 **Transformaciones Extensible Stylesheet Language (XSL)**  
 Un formato de hoja de estilos para los documentos de lenguaje de marcado Extensible (XML). XSL se utiliza para definir la presentación de XML de la misma manera que hojas de estilos en cascada (CSS) se utilizan para definir la presentación del lenguaje de marcado de hipertexto (HTML). [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]utiliza XSL como idioma de traducción entre dos especificaciones.  
  
## <a name="f"></a>F  
 **FINÉS**  
 Mensajes para los que ha definido las SWIFT esquemas y estándares de validación en la Guía de versión SWIFT estándares 2003 financieros.  
  
## <a name="g"></a>G  
 **caché global de ensamblados (GAC)**  
 Caché de código de todo el equipo que almacena los ensamblados instalados específicamente para que los compartan varias aplicaciones del equipo. Las aplicaciones implementadas en la caché global de ensamblados deben tener un nombre seguro.  
  
## <a name="h"></a>H  
 **Protocolo de transferencia de hipertexto seguro (HTTPS)**  
 Transferencia de hipertexto protocolo (HTTP) mediante el protocolo de cifrado de capa de Sockets seguros (SSL).  
  
## <a name="i"></a>I  
 **intercambio**  
 Un mensaje completo consta de partes de mensaje más pequeñas o bloques. Por ejemplo, un SWIFT intercambio en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] se define como la concatenación de una parte del encabezado SWIFT (SWIFT bloques 1, 2, 3), seguido de una parte del cuerpo SWIFT (SWIFT bloquear 4), seguido por una parte del finalizador SWIFT (SWIFT bloquear 5).  
  
## <a name="m"></a>M  
 **mapa**  
 Archivo XML que define la correspondencia entre los registros y campos de una especificación y los de otra. Un mapa contiene un Extensible Stylesheet Language (XSL) hoja de estilos que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se usa para realizar la transformación descrita en la asignación. Puede crearlas en el asignador de BizTalk.  
  
 **tipo de mensaje**  
 Uno de los formatos de mensaje definidos en la Guía de versión de SWIFT estándares, como "Recibir con pago". Tipos de mensajes a menudo se denotan mediante "MT" seguido por un código de tres dígitos.  
  
## <a name="p"></a>P  
 **Identificador de la transacción de pago (PTI)**  
 Un identificador de transacción único, proporcionado por el cliente de inicio, que está asociado a los mensajes de banca relacionadas con los pagos procedentes de bancos, como los mensajes de inicio de pago y avisos de crédito.  
  
 **Directiva**  
 Colección que tiene versión de reglas de negocios.  
  
 **PTI**  
 Identificador de la transacción de pago.  
  
## <a name="r"></a>L  
 **regla**  
 Par de condiciones y acciones.  
  
 **conjunto de reglas**  
 Agrupación lógica de reglas similares. Se puede ver como mecanismo de agrupación o partición del motor de reglas.  
  
## <a name="s"></a>S  
 **esquema**  
 La definición de la estructura de un archivo XML. Un esquema contiene información de la propiedad ya que pertenece a los registros y campos dentro de la estructura.  
  
 **Sin ánimo de telecomunicaciones financieros bancos vinculados en todo el mundo (SWIFT)**  
 Sin ánimo de telecomunicaciones financieros de bancos vinculados en todo el mundo. Una organización que proporciona servicios de mensajería a bancos, corredores de bolsa, administradores de inversiones e infraestructuras de mercado en pagos, Tesoro, títulos y a los intercambios. SWIFT crea un procesamiento de datos compartido en todo el mundo y vínculo de comunicaciones y un lenguaje común para las transacciones financieras internacionales.  
  
 **especificación**  
 Un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]-esquema XML específico. Especificaciones de se crean en el Editor de BizTalk y se pueden basar en estándares del sector (por ejemplo, SWIFT, EDIFACT, X 12 y XML) o en archivos planos (delimitados, posicionales o delimitados y posicionales). El Asignador de BizTalk utiliza especificaciones, abiertas como especificaciones de origen y destino especificaciones, para crear asignaciones.  
  
 **nombre seguro**  
 Un nombre que consta de la identidad de un ensamblado, su nombre de texto simple, el número de versión y la información de referencia cultural (si se proporciona), reforzado por una clave pública y una firma digital que se generan en el ensamblado. Dado que el manifiesto del ensamblado contiene los hash de archivo para todos los archivos que constituyen la implementación del ensamblado, es suficiente para generar la firma digital en el archivo en el ensamblado que contiene el manifiesto del ensamblado. Ensamblados con el mismo nombre seguro deben ser idénticos.  
  
 **Procesamiento directa (STP)**  
 El procesamiento automático de un mensaje a través de varios pasos, no requiere intervención manual. Normalmente se aplica a la ruta de acceso de procesamiento de recepción de un mensaje de SWIFT en una institución financiera para el registro de la transacción resultante en los sistemas internos de la institución financiera; o bien, en la recepción de una instrucción externa o acción en una institución financiera para la transmisión de los mensajes resultantes a través de SWIFT u otras infraestructuras financieros; o bien, desde un sistema interno institución financiera para la transmisión de uno o varios mensajes a través de SWIFT u otras infraestructuras financieros relacionados.  
  
 **Guías de versión SWIFT estándares (SRG)**  
 La publicación de SWIFT que proporciona los estándares actualizados y propuestos para el conjunto de mensajes FIN. Se trata de un conjunto de varios volúmenes de documentos que define el diseño y los campos para cada tipo de mensaje, los valores válidos y formatos para cada campo, las reglas de red que se aplica a cada mensaje y las reglas de uso o prácticas comunes. Esta publicación de CD está disponible mediante el servicio de suscripción de SWIFT.  
  
 **Sistema que originó el finalizador de mensaje (SYS)**  
 Un finalizador anexado por la red SWIFT a los mensajes se entrega a una institución financiera, que indica que el servicio FINÉS generó el mensaje. Algunos ejemplos son las difusiones, las respuestas a las solicitudes de usuario e informes.  
  
## <a name="u"></a>U  
 **Identificador único de envío (URI)**  
 Un identificador generado por los participantes en el programa de hito de pagos de RosettaNet para sincronizar los intercambios de banca intercambios de negocio con.  
  
## <a name="x"></a>X  
  
 **Datos reducidos XML (XDR)**  
 Lenguaje preliminar que se usa para crear un esquema, que identifica la estructura y las restricciones de un documento XML determinado. Datos reducidos XML hace referencia al subconjunto de la especificación del esquema de datos XML que está disponible en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] XML Parser (MSXML) 3.0 y versiones posteriores. Lleva a cabo las mismas tareas básicas que una DTD, pero con más eficacia y flexibilidad. A diferencia de la DTD, lo que requiere su propio lenguaje y sintaxis, XDR utiliza la sintaxis XML para su idioma. A diferencia de XSD, que solo recientemente ha recomendado como una norma, se implementa y están disponible por XDR [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] mucho antes de la existencia de XSD como norma recomendada por el grupo de trabajo de esquema XML de W3C.  
  
 **Definición de esquemas XML (XSD)**  
 Lenguaje propuesto por el grupo de trabajo de esquema XML de W3C para su uso en la definición de esquemas. Los esquemas son útiles para exigir una estructura o restringir a los tipos de datos que pueden utilizar de forma válida en otros documentos XML. Definición de esquemas XML hace referencia a la norma completamente especificada y recomendada actualmente para su uso en la creación de esquemas XML. Porque solo recientemente se finaliza la especificación de XSD, compatibilidad para que solo se puso a disposición con el lanzamiento de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] XML Core Services (MSXML) 4.0. Lleva a cabo las mismas tareas básicas que una DTD, pero con más eficacia y flexibilidad. A diferencia de la DTD, lo que requiere su propio lenguaje y sintaxis, XSD utiliza la sintaxis XML para su idioma. XSD estrechamente es similar y amplía las capacidades de XDR. Ahora, el W3C recomienda el uso de XSD como un estándar para la definición de esquemas XML.