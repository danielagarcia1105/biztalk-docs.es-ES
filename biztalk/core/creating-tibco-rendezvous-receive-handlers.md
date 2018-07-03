---
title: Creación de TIBCO Rendezvous artefactos de recepción del adaptador | Microsoft Docs
description: Crear un puerto de envío, configure las propiedades de transporte para recibir mensajes del adaptador de BizTalk para TIBCO Rendezvous en BizTalk
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d617a97-c165-46bb-b5a7-b66f0c1ff9f2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbe8e3da4e56b7a7d0df0114057f2e17ff1ce333
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982413"
---
# <a name="create-tibco-rendezvous-receive-artifacts"></a>Crear artefactos de recepción de TIBCO Rendezvous
Crear notificaciones o eventos es similar a crear otras llamadas en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En esta sección se explica cómo crear una ubicación de recepción para escuchar mensajes de TIBCO Rendezvous.  

## <a name="events-and-receive-locations"></a>Los eventos y las ubicaciones de recepción
Cualquier sistema TIBCO Rendezvous puede enviar mensajes a su nombre de asunto de elección. El concepto de *eventos* es la generación de mensajes de otros programas de TIBCO Rendezvous.  
  
 En los pasos siguientes se describe el ciclo de vida de una ubicación de recepción:  
  
1.  Se crea la ubicación de recepción.  
  
2.  La ubicación de recepción se asocia con un host.  
  
3.  La ubicación de recepción se enlaza con una orquestación.  
  
4.  La ubicación de recepción se habilita.  
  
5.  La ubicación de recepción recibe mensajes.  
  
> [!IMPORTANT]
>  Cada ubicación de recepción debe tener un nombre único. Dos ubicaciones de recepción no pueden tener el mismo nombre en la misma implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
> 
> [!IMPORTANT]
>  Asimismo, conviene establecer listas de control de acceso (ACL) seguras en las ubicaciones de destino de las ubicaciones de recepción. Por ejemplo, debe establecer listas ACL seguras para el directorio desde el que la ubicación de recepción de archivos toma los mensajes, de modo que solo los usuarios autorizados puedan entregar mensajes en esta ubicación. 

## <a name="create-a-receive-port"></a>Crear un puerto de recepción  
  
1.  En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación.  
  
2.  Haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.  
  
3.  En el **propiedades de puerto de recepción** ventana, en el **General** página, realice lo siguiente:  
  
    1.  En el **nombre** , escriba `ReceiveFromTIBCORV`.  
  
    2.  En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.  
  
    3.  Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.  
  
4.  En el **ubicaciones de recepción** página, realice lo siguiente:  
  
    1.  Haga clic en **Nueva**.  
  
    2.  En el **ubicaciones de recepción** ventana, en el **General** página, escriba el **nombre** de la ubicación de recepción.  
  
    3.  Desde el **tipo** lista desplegable, seleccione el **BizTalkServerIsolatedHost**y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.  
  
    4.  Desde el **canalización de recepción** lista desplegable, seleccione **XMLReceive** o cualquier canalización equivalente. 
  
    5.  En el **programación** página, seleccione el **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.  
  
    6.  Seleccione el **habilitar ventana de servicio** casilla de verificación.  
  
    7.  Haga clic en **Aceptar**.  
  
5.  En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar los documentos en el puerto seleccionado.  
  
6.  En el **seguimiento** , seleccione el seguimiento de cuerpos de mensaje deseado y las propiedades de mensaje de seguimiento.  
  
7.  Haga clic en **Aceptar**.  

## <a name="set-the-transport-properties"></a>Establecer las propiedades de transporte
Cuando configure el Adaptador de Microsoft BizTalk para TIBCO Rendezvous para escuchar mensajes, debe especificar los nombres de asunto que debe escuchar. Ésta es la única propiedad necesaria.  
  
 
1.  En el cuadro de diálogo Propiedades de transporte de TIBCO Rendezvous, expanda **propiedades de adaptador necesarias**, escriba el **nombre de asunto de Rendezvous**.  
  
     Se trata del nombre de asunto (se permiten caracteres de comodín de Rendezvous) que escucha el adaptador. En el escenario de implementación más sencillo, es la única propiedad necesaria.  
  
     ![](../core/media/sadp-tibcorecvtranspropertiess.gif "SAdp_TIBCORecvTransPropertiess")  
  
2.  En el **configuración de agente de escucha certificada**, proporcione el nombre reutilizable y el nombre de archivo de libro de contabilidad si desea mensajes certificados.  
  
     Esto es obligatorio si está definiendo una cola distribuida. Si no son necesarios mensajes certificados, deje en blanco estas entradas. Tanto el nombre del archivo de contabilidad como el nombre reutilizable deben ser únicos en todos los puertos definidos en este host y en otros programas de TIBCO Rendezvous en ejecución en este host. Si no es el caso, la interfaz de usuario no lo detecta, pero se registra un error en tiempo de ejecución.  
  
3.  En el **configuración de cola distribuida**, si la cola distribuida no es necesaria, no cambie las entradas.  
  
     Los siguientes valores se usan junto con un grupo de BizTalk Server. El adaptador de BizTalk para TIBCO Rendezvous usa estos valores en las llamadas de API a TIBCO RV.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de archivo de libro de contabilidad**|Nombre de archivo de contabilidad para el proceso de escucha (o miembro del grupo) certificado. El valor predeterminado es Null.<br /><br /> Si no se especifica un valor, se usa la contabilidad de memoria.|  
    |**Nombre reutilizable**|Nombre reutilizable para el proceso de escucha (o miembro del grupo) certificado. El valor predeterminado es Null.<br /><br /> Es necesario un nombre reutilizable para sobrevivir a un proceso que se está reiniciando. Si no se especifica un valor, se usa un nombre generado (no reutilizable).|  
  
     Las colas distribuidas son útiles si se implementa una ubicación de recepción de TIBCO Rendezvous en un grupo BizTalk Server. En tal caso, introduzca los intervalos y los valores de directivas deseados. Tanto intervalos de activación como intervalos de latidos se proporcionan tal cual para TIBCO Rendezvous. Dado que los intervalos deben ser idénticos en todos los participantes de una cola distribuida, los valores solo se especifican una vez. Con las directivas, los valores podrían fácilmente ser diferentes en cada host. Todos los valores de directivas siguen la misma sintaxis de host:valor separados por dos puntos, con las parejas separadas por punto y coma.  
  
     Por ejemplo, **host1:10; host2:20; host3:30**  
  
     El nombre de host debe ser un nombre de host DNS válido o una dirección IP. Para cada una de estas directivas, el adaptador encuentra el valor asociado con su host y lo usa con la API de TIBCO Rendezvous.  
  
     Si los valores deben ser idénticos en todos los equipos, puede escribir un valor simple en lugar de la lista de pares de nombre-valor Nombre_valor (por ejemplo, **20**).  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Intervalo de activación**|Directiva de peso de programador usada para esta cola distribuida. Es el intervalo de tiempo sin un mensaje de latido del programador, tras el cual TIBCO RV activa un nuevo programador. El valor predeterminado es de 20 segundos.|  
    |**Intervalo de latido**|Intervalo de latido usado en esta cola distribuida. Se usa con el parámetro Grupo de BizTalk Server. El adaptador de BizTalk para TIBCO Rendezvous usa estos valores en las llamadas de API a TIBCO RV. El valor lo usa la instancia del adaptador que es el programador activo para el grupo y transmite mensajes de latido en dicho intervalo (en segundos). Valor predeterminado es 10.|  
    |**Directiva de peso de programador**|De forma predeterminada (valor nulo), todos los miembros de un grupo tienen las mismas oportunidades de ser programador. Una lista de valores de pareja host-peso proporciona una directiva de peso diferente. El valor predeterminado es Null.|  
    |**Directiva de capacidad de trabajo**|Directiva de capacidad de trabajo usada para esta cola distribuida. Este valor indica cuántas tareas simultáneas puede gestionar un miembro del grupo. Si no se especifica nada, el valor predeterminado es 1. Una lista de valores de pareja host-capacidad proporciona una directiva de capacidad diferente.|  
    |**Directiva de peso de trabajo**|La directiva de peso de trabajo usada para esta cola distribuida. Este valor proporciona un valor de peso para ayudar a TIBCO a asignar tareas en una cola distribuida. A los trabajadores disponibles se le asignan tareas comenzando por las de mayor peso. Valor predeterminado es 1.|  
  
4.  Expanda **configuración General** y escriba toda la información necesaria para la conexión al servidor TIBCO Rendezvous.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Sustituto de comodín de apéndice**|Especifique un sustituto de texto comodín. Los nombres de asunto que escucha una ubicación de recepción se usan para generar el espacio de nombres del destino XML en los mensajes resultantes. De forma predeterminada, el adaptador reemplaza cualquier comodín '>' con el texto GTWILDCARD en los mensajes generados. Puede especificar un comodín diferente en este campo.|  
    |**Número de página de códigos**|Identifica la página de códigos que usa el originador del mensaje para codificar las cadenas contenidas en los mensajes entrantes. El valor predeterminado es 65001. (El adaptador no admite tener la misma asuntos del mensaje generados a partir de dos entornos de página de códigos diferentes).|  
    |**Sustituto de comodín de elemento**|Especifique un sustituto de texto comodín diferente, los nombres de asunto que escucha una ubicación de recepción se usan para generar el espacio de nombres XML en los mensajes resultantes. De forma predeterminada, el adaptador reemplaza cualquier comodín '*' con el texto STARWILDCARD en los mensajes generados. Puede especificar un comodín diferente en este campo.|  
    |**Nombre de la cola de eventos**|Especifique un nombre que se va a usar al crear el objeto de cola Rendezvous. Se proporciona por comodidad, porque los mensajes de registro asociados muestran el nombre de la cola de eventos. Valor predeterminado es empty.|  
    |**Filter**|Si especifica caracteres comodín al escuchar nombres de asunto, es posible que la orquestación de destino solo esté interesada en un subconjunto del conjunto de asuntos que podrían alcanzarse, potencialmente muy grande. Para minimizar el impacto en BizTalk Server y el acceso asociado a las bases de datos, puede especificar qué mensajes deben enviarse a BizTalk Server. Esta entrada contiene una lista separada por punto y coma de nombres de asunto (no se permiten caracteres comodín). Los mensajes que coincidan con un nombre de asunto especificado por comodín, pero cuyo nombre de asunto se encuentre en esta lista, se desechan (no se envían a BizTalk Server). La lógica del filtro puede invertirse anteponiendo un carácter '!' al valor del filtro. El valor predeterminado es vacío (sin filtro).|  
    |**Asignar tipos no compatibles a cadena**|Si los tipos no compatibles generan un error o se asignan a una cadena. Puede usarse si se usa el adaptador con una versión más reciente de TIBCO Rendezvous, en la cual se hayan agregado nuevos tipos.|  
    |**Miembro del grupo de BizTalk**|Si se configura en True, deberán configurarse los parámetros de Cola distribuida (consulte el nodo Configuración de cola distribuida) y de Escucha certificada (consulte el nodo Configuración de escucha certificada). El valor predeterminado es False.|  
    |**Ruta de acceso**|Configúrelo para que señale los binarios de TIBCO Rendezvous, en caso de que dicha información no se encuentre aún en la variable de entorno PATH.|  
    |**Conservar el orden**|Si el adaptador distribuye los mensajes entrantes a BizTalk Server en el mismo orden en que se reciben (por ejemplo, usando un único subproceso de distribución). Tenga en cuenta que si no se configuran los parámetros de Mensajes certificados, ello no supone que el adaptador reciba el mensaje en el mismo orden en que se enviaron (refiriéndose a un único origen).|  
    |**Identificador de ubicación de recepción**|El nombre de la ubicación de recepción.|  
    |**Reserved**|Campo reservado para uso especial.|  
  
5.  Expanda el **transporte Rendezvous**y escriba toda la información necesaria para la comunicación entre los programas y daemons de TIBCO Rendezvous.  
  
     El **transporte (red, Daemon, servicio)** especifica cómo los daemons de TIBCO Rendezvous intercambian mensajes. Estos valores se envían tal cual a la API de TIBCO Rendezvous. Si se usan los valores predeterminados (vacío), se usará la estrategia de comunicación predeterminada.  
  
     Un transporte de TIBCO Rendezvous define el ámbito de entrega; es decir, el conjunto de posibles destinos para los mensajes que envía. Este conjunto de propiedades define un transporte.  
  
    |Parámetro|Descripción|  
    |---------------|-----------------|  
    |**Demonio**|Escriba el identificador numérico para el parámetro Daemon del transporte Rendezvous.|  
    |**Red**|Escriba el nombre del parámetro Red de Rendezvous.|  
    |**Nombre de servicio** `e`|Escriba el nombre del servicio de transporte Rendezvous.|  
  
6.  Proporcione credenciales mediante el inicio de sesión único (SSO).  
  
     Hay dos métodos que puede utilizar para tener acceso al sistema TIBCO Rendezvous. Puede usar credenciales (parámetros de nombre de usuario y contraseña) o el inicio de sesión único.  
  
    1.  Seleccione **Sí** en el **usar SSO** utilizar inicio de sesión único.  
  
        > [!NOTE]
        >  Consulte [seguridad](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) para obtener información acerca de cómo configurar el inicio de sesión único.  
  
    2.  Seleccione una aplicación afiliada de la lista.  
  
         Una aplicación afiliada, creada por la herramientas de Inicio de sesión único empresarial, representa una aplicación como TBCO Rendezvous. El adaptador de Microsoft BizTalk para TIBCO Rendezvous usa las credenciales de un usuario de la aplicación. Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.  
  
        > [!NOTE]
        >  Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications1.md).  
  
7.  Después de proporcionar toda la información necesaria, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
     Debe establecer los parámetros de conexión para que el Adaptador de BizTalk para TIBCO Rendezvous reciba mensajes de TIBCO Rendezvous.  
  

   
## <a name="next-steps"></a>Pasos siguientes
  
-   [Recibir esquemas y procesar eventos](../core/using-tibco-rendezvous-receive-ports-from-biztalk-server.md) 
  
-   [Asignación de mensajes](../core/message-mapping-in-tibco-rendezvous.md)  
  
-   [Asignación de tipos de datos](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)  
  
-   [Propiedades de contexto del mensaje (controladores de recepción)](../core/biztalk-server-message-context-properties-receive-handlers.md)