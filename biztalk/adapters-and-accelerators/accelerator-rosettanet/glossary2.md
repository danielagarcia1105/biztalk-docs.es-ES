---
title: Glosario de Acelerador para RosettaNet en BizTalk Server | Documentos de Microsoft
description: Común de términos y definiciones para conocer y aprender a usar el Acelerador de BizTalk para RosettaNet
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d98a5ed4-adc5-4ca9-b9d9-38ab02a0bda6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd89d75b0d36359fcf59f7edae0bb950a7196ca7
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22211732"
---
# <a name="glossary"></a>Glosario
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] usa el siguiente Glosario de términos y definiciones.  

  
## <a name="a"></a>A  
 **adaptador de la aplicación**  
 Aplicación que implementa la interfaz de adaptador de la aplicación. El mecanismo de notificación de la aceptación de un mensaje entrante de acción (solicitud o respuesta) invoca al adaptador de la aplicación. Implementa dos métodos: `BeginNotify` y `EndNotify`. El servicio de respuesta pública invoca el método `BeginNotify` , mientras que el servicio de respuesta privado estándar invoca el método `EndNotify` . La llamada al método `Notify` significa que el mensaje se guardó correctamente en la tabla MessagesToLOB.  
  
 **Dirección URL de acción**  
 La dirección URL de socio comercial a la que la organización principal transmite un mensaje de acción durante un proceso asincrónico, por ejemplo, http://FabrikamServer/BTARNApp/RNIFReceive.aspx.  
  
## <a name="b"></a>B  
 **Acelerador de BizTalk para RosettaNet**  
 Un producto complementario a BizTalk Server que ayuda a las organizaciones a crear RosettaNet Implementation Framework (RNIF)-soluciones compatibles con.  
  
 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Administración**  
 Microsoft [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] aplicación que le permite describir plantillas de proceso y administrar acuerdos de socios.  
  
 **Editor de BizTalk**  
 Herramienta que puede crear, editar y administrar las especificaciones. Con el Editor de BizTalk puede crear una especificación basada en una plantilla de especificación, un esquema existente, ciertos tipos de instancias del documento o una especificación en blanco.  
  
 **Diseñador de orquestaciones de BizTalk**  
 Herramienta de diseño que puede utilizar para crear dibujos que describen procesos empresariales ejecutables de larga ejecución de acoplamiento flexible. El dibujo de la programación XLANG se compila en una programación XLANG que se usa para ejecutar el proceso empresarial automatizado.  
  
 **Servidor BizTalk Server**  
 Un producto de Microsoft para la automatización de procesos empresariales y la integración de aplicaciones en y entre empresas. BizTalk Server proporciona un desarrollo eficaz basada en Web y entorno de ejecución que integra débilmente acoplado, procesos empresariales de larga duración, en y entre empresas.  
  
 Características de BizTalk Server incluyen la composición de las programaciones XLANG nuevas y existentes; integración entre las aplicaciones existentes; la definición de especificaciones de documentos y las transformaciones de especificaciones; y la supervisión y el registro de actividad en tiempo de ejecución.  
  
 El servidor proporciona una puerta de enlace estándar para enviar y recibir documentos a través de Internet, y ofrece una gama de servicios que ayuda a garantizar la integridad, entrega, seguridad y compatibilidad de los datos con el marco de trabajo de BizTalk y otros formatos de documentos clave.  
  
 **BtarnClean**  
 Una utilidad para limpias artefactos BTARN en un equipo.  
  
 **Acción empresarial**  
 Mensaje de RosettaNet que incluye contenido empresarial como una solicitud de pedido de compra o una solicitud de una oferta. Junto con las señales de negocios, estas acciones constituyen los elementos necesarios para completar la actividad de negocio especificada por un proceso de interfaz de socio determinado (PIP).  
  
 **Actividad económica (BAM) de supervisión**  
 Un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] característica que proporciona a los usuarios empresariales una vista en tiempo real de los procesos empresariales heterogéneos. Esto les permite tomar decisiones empresariales importantes.  
  
 **señal de negocios**  
 Mensaje de RosettaNet, como un ReceiptAcknowledgement o una excepción, que se intercambia entre dos aplicaciones de red de RosettaNet para comunicar determinados eventos en la ejecución de una instancia PIP. Junto con las acciones de negocios, estas señales constituyen los elementos necesarios para completar la actividad de negocio especificada por un proceso PIP determinado.  
 
  
## <a name="c"></a>C  
 **CertWizard**  
 Utilidad para importar un certificado de firma o cifrado de un archivo .cer (.der) o .pfx (. p12) en un almacén privado o público para su uso con BTARN. Un archivo .pfx, también conocido como Intercambio de información personal–PKCS #12, normalmente está protegido mediante contraseña ya que contiene una clave privada que se utiliza para la firma y el descifrado. Un archivo .cer (archivo de certificado) contiene la clave pública para el cifrado y la validación de la firma.  
  
 **Para la industria química normas europeas de química de intercambio de datos (CIDX)**  
 Normas uniformes de intercambio de datos desarrolladas específicamente para la compra, venta y entrega de productos químicos. Estas normas se basan en los estándares universalmente reconocidos para el intercambio electrónico de datos: XML. BTARN admite las normas europeas de química CIDX.  
  
 **Clúster**  
 Grupo de procesos de negocio de alto nivel, como administración de pedidos, administración de inventario o servicio y soporte técnico. Los clústeres dirigidos por RosettaNet representan procesos empresariales básicos para el sector de la cadena de suministro.  
  
## <a name="d"></a>D  
 **Número de sistema de numeración Universal (D-U-N-S) de datos**  
 Número generado de forma secuencial de nueve dígitos que identifica exclusivamente las ubicaciones de negocios y tiene ámbito global.  
  
 **encabezado de entrega**  
 Una parte de un mensaje de RosettaNet. El encabezado de entrega es un documento XML que identifica al remitente del mensaje, el destinatario y la información de la instancia de mensaje.  
  
 **organización de destino**  
 Organización que se ha designado como destino para los documentos en un puerto de mensajería.  
  
 **algoritmos digitales**  
 Algoritmo que toma un mensaje como entrada y genera un hash o un resumen del mismo, un conjunto de longitud fija de bits que dependen del contenido del mensaje de una manera altamente compleja. Los criterios de diseño incluyen dificultar extremadamente a cualquiera la falsificación de una síntesis o el cambio de un mensaje sin cambiar su síntesis. Las aplicaciones que utilizan normalmente algoritmos de síntesis están en esquemas de firma digital y autenticación de mensajes. Los algoritmos más utilizados incluyen MD5 y SHA1. BTARN admite tanto MD5 y SHA1 para los mensajes entrantes y solo SHA1 para los mensajes salientes.  
  
 **definición de documento**  
 Conjunto de propiedades que representa un documento específico. Las propiedades de la definición de documento incluyen un puntero a una especificación de documento y pueden incluir campos de seguimiento global y criterios de selección.  
  
 **instancia de documento**  
 Una representación de los datos reales que se envían a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Una instancia de documento difiere de una especificación de documento en que la especificación define la estructura de los datos, mientras que una instancia de documento es una representación de los datos específicos que se encuentran en una estructura.  
  
 **definición de tipo de documento (DTD)**  
 Definición estándar que especifica qué elementos y atributos pueden estar presentes en otros elementos y atributos y que especifica las restricciones en su orden, frecuencia y contenido.  
  
 **transacción de doble acción**   
 Proceso en el que un iniciador envía una acción de solicitud y recibe una señal, seguida de una acción de respuesta desde el servicio de respuesta. El iniciador finaliza el proceso mediante el envío de una señal a la acción de respuesta.  
  
## <a name="e"></a>E  
 **Lenguaje de marcado extensible (XML)**  
 Especificación desarrollada por World Wide Web Consortium (W3C) que permite a los diseñadores crear etiquetas personalizadas más allá de las capacidades de HTML estándar. Mientras que HTML usa solo las etiquetas predefinidas para describir los elementos de la página, XML permite que el desarrollador de la página defina las etiquetas. Las etiquetas para prácticamente cualquier elemento de datos, como un producto o una cantidad debida, pueden utilizarse para aplicaciones específicas. Esto permite que las páginas web funcionen como registros de la base de datos.  
  
 **Transformaciones Extensible Stylesheet Language (XSL)**  
 Formato de hoja de estilos para documentos XML. XSL se utiliza para definir la presentación de XML, al igual que las hojas de estilo en cascada (CSS) se usan para definir la presentación de HTML. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] utiliza XSL como idioma de traducción entre dos especificaciones.  
  
## <a name="g"></a>G  
 **Identificación empresarial global (GBI)**  
 Identificador único para identificar entidades comerciales. RosettaNet utiliza el sistema de numeración de nueve dígitos de Dun and Bradstreet (DUNS) como GBI.  
  
## <a name="h"></a>H  
 **organización principal**   
 Alias para identificar a su organización.  
  
## <a name="i"></a>I  
 **iniciador**  
 Función de una organización en un proceso de notificación o transacción que inicia un proceso a un socio comercial.  
  
## <a name="l"></a>L  
 **Aplicación línea de negocio (LOB)**  
 Aplicación que se comunica con BTARN como el sistema back-end.  
  
 **Utilidad de bucle invertido**  
 Utilidad para que los desarrolladores generen automáticamente un acuerdo de bucle invertido que es una copia reflejada de un acuerdo de principal a asociado. Esto le permite realizar intercambios de mensajes de principal a asociado y de asociado a principal en un único equipo.  
  
## <a name="m"></a>M  
 **mapa**  
 Archivo XML que define la correspondencia entre los registros y campos de una especificación y los de otra. Un mapa contiene un XSL hoja de estilos que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se usa para realizar la transformación descrita en la asignación. Las asignaciones se crean en el Asignador de BizTalk.
  
 **Mi organización**  
 Representa a su organización en un acuerdo entre socios comerciales.   
  
 **Extensiones de correo de Internet con varios fines (MIME)**  
 Extensión del protocolo de correo electrónico de Internet que le permite usar el protocolo para intercambiar los distintos tipos de archivos de datos en Internet: audio, vídeo, imágenes y programas de aplicación.  
  
## <a name="n"></a>N  
 **sin repudio**  
 Manera de asegurarse de que el remitente de un mensaje no puede negarse más adelante a reconocer al remitente que envió el mensaje y de que el destinatario no puede negar que recibió el mensaje. Un sin repudio de un mensaje entrante requiere que el receptor guarde el mensaje y que el mensaje incluya una firma digital mediante el certificado de firma del remitente para asegurar su autenticidad. Un sin repudio de un mensaje saliente requiere guardar el mensaje de confirmación (mensaje entrante del destinatario del primer mensaje) y que el mensaje incluya la firma digital de la síntesis del mensaje original mediante el certificado de firma del destinatario.   
  
 **notificación**  
 Tipo de proceso RNIF 1.1 en el que el iniciador informa al servicio de respuesta mediante un solo mensaje. Se espera que el servicio de respuesta responda con una señal de negocios como confirmación.  
  
 **Notificación de error (PIP 0A1)**  
 PIP especial que indica los errores inesperados en el proceso. El iniciador o el servicio de respuesta puede iniciar una notificación de error. Hace referencia a un proceso existente o intercambiado con anterioridad. Tras la recepción de un 0A1, la parte receptora se asegura de que el proceso al que hace referencia se considera no válido.  
  
## <a name="o"></a>O  
 **Organización**  
 Socio comercial o unidad de negocio que puede realizar transacciones comerciales.  
  
## <a name="p"></a>P  
 **Empaquetado**  
 El proceso de convertir un mensaje de RosettaNet en su representación XML y viceversa.  
  
 **Proceso de interfaz de socio (PIP)**  
 Un PIP describe un conjunto de documentos empresariales y los detalles del contrato, incluidos los detalles de contenido del documento.  
  
 **Documento de la especificación de PIP**  
 Documento que contiene instrucciones sobre la configuración que se va a usar al crear una configuración de proceso en la consola de administración de BTARN. Descargue el documento de especificación de PIP y el PIP de la organización RosettaNet, en RosettaNet.org. Documento que contiene instrucciones sobre la configuración que se va a usar al crear una configuración de proceso en la consola de administración de BTARN. Descargue el documento de especificación de PIP y el PIP de la organización RosettaNet, en RosettaNet.org.  
  
 **encabezado de preámbulo**  
 Nodo XML que identifica el nombre y la versión del estándar con el que es compatible un mensaje de negocio. Está empaquetado junto con otros encabezados para formar un mensaje de RosettaNet completo. También se denomina preámbulo.  
  
 **proceso privado**   
 Procesos empresariales internos de una organización. BTARN implementa procesos privados como orquestaciones de BizTalk de larga duración.  
  
 **Proceso perfil de configuración de configuración (equipos)**  
 Determina cómo se ejecuta un acuerdo de socio. El perfil de equipos se utiliza para especificar los detalles de configuración de un proceso de interfaz de socio (PIP) RosettaNet. Todos los valores de configuración especificados en un mapa de especificación del PIP de RosettaNet a un elemento en el perfil de equipos. Puede utilizar un perfil de equipos para varios acuerdos de socios comerciales.  
  
 **port**  
 Ubicación con nombre que utiliza una implementación específica. En el diseñador de orquestaciones de BizTalk, ubicación a la que se envían los mensajes o desde la cual se reciben, y tecnología que se utiliza para implementar la acción de comunicación. La ubicación sólo se identifica por el nombre del puerto.  
  
 **proceso público**   
 Procesos empresariales que implican la integración con socios comerciales como procesos públicos. BTARN implementa procesos públicos como orquestaciones de BizTalk de larga duración. Una orquestación de proceso público se ejecuta en el lado del iniciador y otra, en el lado del servicio de respuesta. El programa de instalación de BTARN proporciona versiones de orquestaciones de proceso público de servicio de respuesta y de iniciador para RNIF 1.1 y RNIF 2.01. Estas orquestaciones de proceso público implementan todos los procesos RNIF. Los procesos públicos ocultan la complejidad de RNIF del resto de los componentes. Además de aplicar el flujo de mensajes compatible con RNIF, el proceso público también determina la configuración de seguimiento predeterminada y proporciona información de estado de proceso en tiempo de ejecución.  
  
## <a name="r"></a>L  
 **servicio de respuesta**  
 La función de una organización en un proceso de notificación o transacción que responde a una solicitud de un socio comercial.  
  
 **Marco de implementación de RosettaNet (RNIF)**  
 Un marco de estándares que proporciona instrucciones de implementación para esas compañías que va a crear componentes de aplicación de software interoperable que ejecutan PIP.  
  
 **Mensaje de RosettaNet**  
 El agrupamiento lógico del encabezado preámbulo, el encabezado de entrega (en el caso de 2.0 RNIF), el encabezado de servicio y el contenido de servicio.  
  
 **Objeto de RosettaNet**  
 Un mensaje de RosettaNet con doble cifrado para ser entregado en el Marco de implementación de RosettaNet, versión 1.1.  
  
## <a name="s"></a>S  
 **schema**  
 La definición de la estructura de un archivo XML. Un esquema contiene información de la propiedad ya que pertenece a los registros y campos de la estructura.  
  
 **contenido del servicio**  
 El componente principal de los mensajes de RosettaNet. Es un nodo XML que representa el contenido empresarial especificado por un determinado PIP.  
  
 **encabezado de servicio**  
 Un documento XML que identifica las partes asociadas a un mensaje de negocio, incluido el PIP, la acción y actividad económica, enviar y recibir servicios, socios comerciales y roles.  
  
 **Dirección URL de señal**  
 Dirección URL a la que la organización principal transmite un mensaje de señal. Por ejemplo, http://FabrikamServer/BTARNApp/RNIFReceive.aspx.  
  
 **notificación de acción única**  
 Proceso en el que el iniciador envía un mensaje de acción única y el servicio de respuesta responde con un mensaje.  
  
 **Especificación**  
 Un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]-esquema XML específico. Cree las especificaciones en el Editor de BizTalk y se pueden basar en estándares del sector, como EDIFACT, X 12 y XML, o en los archivos sin formato, como delimitados, posicionales o delimitados y posicionales. El Asignador de BizTalk utiliza especificaciones, abiertas como especificaciones de origen y destino especificaciones, para crear asignaciones.  
  
 **Dirección URL de la sincronización**  
 La dirección URL que la organización principal se utiliza para establecer transacciones sincrónicas con el socio comercial, por ejemplo, http://FabikamServer/BTARNApp/RNIFReceive.aspx.  
  
 **transacción sincrónica**  
 Un proceso en el que el iniciador devuelve una respuesta (doble acción) o señal (acción única) en el mismo estado HTTP sin cerrar la conexión.  
  
## <a name="t"></a>T  
 **socio comercial**  
 Organización externa o con la que su organización intercambia datos electrónicos.  
  
 **acuerdo de socio comercial**  
 Acuerdo entre su organización y su socio comercial. Acuerdo de socio comercial hace referencia a un perfil de configuración de proceso, organización principal y socios, y contiene la configuración específica del acuerdo.  
  
 **transacción**  
 Proceso de RNIF 1.1 donde el iniciador envía un mensaje de RosettaNet, recibe una señal, recibe un mensaje de RosettaNet como una respuesta y envía una señal de confirmación.  
  
## <a name="v"></a>V  
 **adaptador de validación**  
 Aplicación que implementa la interfaz de adaptador de validación. El servicio de respuesta pública invoca el adaptador de validación cuando recibe un mensaje de acción (solicitud o respuesta). Puede incluir cualquier conjunto de reglas de validación que puede requerir una empresa antes de aceptar un mensaje entrante. BTARN realiza de forma nativa la validación en la canalización de recepción y en orquestaciones públicas.  
  
## <a name="x"></a>X  
 **Programación XLANG**  
 Lenguaje específico de XML que describe los procesos empresariales y la integración de back-end. Los procesos empresariales específicos en BTARN se expresan en el lenguaje XLANG. La programación XLANG se guarda con la extensión de nombre de archivo .skx.  
  
