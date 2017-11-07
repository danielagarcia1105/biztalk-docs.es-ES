---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 48eb0c1694168fb1acf840a52dc793d0ed943a19
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="setting-tibco-rendezvous-receive-transport-properties"></a>Configuración de propiedades de transporte de recepción de TIBCO Rendezvous
Cuando configure el Adaptador de Microsoft BizTalk para TIBCO Rendezvous para escuchar mensajes, debe especificar los nombres de asunto que debe escuchar. Ésta es la única propiedad necesaria.  
  
 Use este procedimiento para especificar las propiedades.  
  
## <a name="enter-tibco-rendezvous-transport-properties"></a>Especifique las propiedades de transporte de TIBCO Rendezvous  
  
1.  En el cuadro de diálogo Propiedades de transporte de TIBCO Rendezvous, expanda **propiedades de adaptador necesarias**, escriba la **nombre de asunto de Rendezvous**.  
  
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
  
     Si los valores son idénticos en todos los equipos, puede escribir un valor simple en lugar de la lista de pares de nombre: valor Nombre_valor (por ejemplo, **20**).  
  
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
    |**Número de página de códigos**|Identifica la página de códigos que usa el originador del mensaje para codificar las cadenas contenidas en los mensajes entrantes. Valor predeterminado es 65001. (El adaptador no admite tener los mismos asuntos del mensaje generados a partir de dos entornos de página de códigos diferente.)|  
    |**Sustituto de comodín de elemento**|Especifique un sustituto de texto comodín diferente, los nombres de asunto que escucha una ubicación de recepción se utilizan para generar el espacio de nombres XML en los mensajes resultantes. De forma predeterminada, el adaptador reemplaza cualquier comodín '*' con el texto STARWILDCARD en los mensajes generados. Puede especificar un comodín diferente en este campo.|  
    |**Nombre de la cola de eventos**|Especifique un nombre que se va a usar al crear el objeto de cola Rendezvous. Se proporciona por comodidad, porque los mensajes de registro asociados muestran el nombre de la cola de eventos. Valor predeterminado está vacío.|  
    |**Filter**|Si especifica caracteres comodín al escuchar nombres de asunto, es posible que la orquestación de destino solo esté interesada en un subconjunto del conjunto de asuntos que podrían alcanzarse, potencialmente muy grande. Para minimizar el impacto en BizTalk Server y el acceso asociado a las bases de datos, puede especificar qué mensajes deben enviarse a BizTalk Server. Esta entrada contiene una lista separada por punto y coma de nombres de asunto (no se permiten caracteres comodín). Los mensajes que coincidan con un nombre de asunto especificado por comodín, pero cuyo nombre de asunto se encuentre en esta lista, se desechan (no se envían a BizTalk Server). La lógica del filtro puede invertirse anteponiendo un carácter '!' al valor del filtro. El valor predeterminado es vacío (sin filtro).|  
    |**Asignar tipos no compatibles a cadena**|Si los tipos no compatibles generan un error o se asignan a una cadena. Puede usarse si se usa el adaptador con una versión más reciente de TIBCO Rendezvous, en la cual se hayan agregado nuevos tipos.|  
    |**Miembro del grupo de BizTalk**|Si se configura en True, deberán configurarse los parámetros de Cola distribuida (consulte el nodo Configuración de cola distribuida) y de Escucha certificada (consulte el nodo Configuración de escucha certificada). El valor predeterminado es False.|  
    |**Ruta de acceso**|Configúrelo para que señale los binarios de TIBCO Rendezvous, en caso de que dicha información no se encuentre aún en la variable de entorno PATH.|  
    |**Conservar el orden**|Si el adaptador distribuye los mensajes entrantes a BizTalk Server en el mismo orden en que se reciben (por ejemplo, usando un único subproceso de distribución). Tenga en cuenta que si no se configuran los parámetros de Mensajes certificados, ello no supone que el adaptador reciba el mensaje en el mismo orden en que se enviaron (refiriéndose a un único origen).|  
    |**Identificador de ubicación de recepción**|El nombre de la ubicación de recepción.|  
    |**Reservado**|Campo reservado para uso especial.|  
  
5.  Expanda el **transporte Rendezvous**y escriba toda la información necesaria para la comunicación entre los programas y daemons de TIBCO Rendezvous.  
  
     El **transporte (red, Daemon, servicio)** especifica cómo los daemons de TIBCO Rendezvous intercambian mensajes. Estos valores se envían tal cual a la API de TIBCO Rendezvous. Si se usan los valores predeterminados (vacío), se usará la estrategia de comunicación predeterminada.  
  
     Un transporte de TIBCO Rendezvous define el ámbito de entrega; es decir, el conjunto de posibles destinos para los mensajes que envía. Este conjunto de propiedades define un transporte.  
  
    |Parámetro|Description|  
    |---------------|-----------------|  
    |**Demonio**|Escriba el identificador numérico para el parámetro Daemon del transporte Rendezvous.|  
    |**Red**|Escriba el nombre del parámetro Red de Rendezvous.|  
    |**Nombre de servicio**`e`|Escriba el nombre del servicio de transporte Rendezvous.|  
  
6.  Proporcione credenciales mediante el inicio de sesión único (SSO).  
  
     Hay dos métodos que puede utilizar para tener acceso al sistema TIBCO Rendezvous. Puede usar credenciales (parámetros de nombre de usuario y contraseña) o el inicio de sesión único.  
  
    1.  Seleccione **Sí** en el **usar SSO** usar Single Sign-On.  
  
        > [!NOTE]
        >  Vea [seguridad](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) para obtener información acerca de cómo configurar SSO.  
  
    2.  Seleccione una aplicación afiliada de la lista.  
  
         Una aplicación afiliada, creada por la herramientas de Inicio de sesión único empresarial, representa una aplicación como TBCO Rendezvous. El adaptador de Microsoft BizTalk para TIBCO Rendezvous usa las credenciales de un usuario de la aplicación. Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.  
  
        > [!NOTE]
        >  Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications1.md).  
  
7.  Después de proporcionar toda la información necesaria, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
     Debe establecer los parámetros de conexión para que el Adaptador de BizTalk para TIBCO Rendezvous reciba mensajes de TIBCO Rendezvous.  
  
## <a name="see-also"></a>Vea también  
 [Creación de controladores de recepción de TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)