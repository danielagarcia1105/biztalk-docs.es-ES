---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: b4fabb9146b4f559dd1a41b6e3b7da5ce9489d1f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015275"
---
# <a name="how-to-set-tibco-rendezvous-transport-properties"></a>Establecimiento de propiedades de transporte de TIBCO Rendezvous
Las propiedades de transporte de TIBCO Rendezvous se usan para el tiempo de ejecución. En el **propiedades de transporte** pantalla, Establece los parámetros de conexión que identifican el dominio TIBCO Rendezvous donde desea publicar los mensajes generados.  
  
## <a name="enter-tibco-rendezvous-transport-properties"></a>Especifique las propiedades de transporte de TIBCO Rendezvous  
  
1.  En el **propiedades de transporte de TIBCO Rendezvous** pantalla, expanda **propiedades de remitente certificado** y escriba la información siguiente.  
  
     ![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre del libro de contabilidad**|El valor predeterminado es en blanco. Nombre del archivo de contabilidad que se va a usar para la entrega de mensajes certificados persistentes. Use solo las unidades locales.|  
    |**Nombre reutilizable**|El valor predeterminado es en blanco. Nombre reutilizable correspondiente que se va a usar para la entrega de mensajes certificados. El nombre debe ser único entre todos los nombres de correspondientes de mensajes certificados en la red.|  
  
2.  Expanda **credenciales** y escriba la siguiente información de conexión al servidor.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Contraseña**|El valor predeterminado es en blanco. Contraseña para iniciar sesión en un demonio TIBCO Rendezvous.|  
    |**Nombre de usuario.**|El valor predeterminado es en blanco. Nombre de usuario para el demonio TIBCO Rendezvous.|  
  
3.  Expanda **configuración General** y escriba la siguiente información de conexión al servidor TIBCO Rendezvous.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Número de página de códigos**|El valor predeterminado es 65001 (página de códigos para la codificación UTF-8). Ésta es la página de códigos que usa el SDK de TIBCO Rendezvous para la codificación de Cadena.|  
    |**Nombre de sujeto predeterminado**|Valor predeterminado está vacío. El nombre del sujeto está establecido en la orquestación. Si se usa un puerto para un tipo de mensaje, se puede proporcionar un nombre de sujeto predeterminado y se pueden simplificar las orquestaciones quitando la necesidad de establecer la propiedad del nombre de sujeto.|  
    |**Habilitar lote de tiempo**|El valor predeterminado es False. Habilitar/Deshabilitar característica de lote de tiempo de TIBCO Rendezvous.|  
    |**Asignar tipos no compatibles a cadena**|Valor predeterminado es True. Si es true, los tipos no compatibles se asignan a la cadena si es posible. Si es False, se genera un error en tiempo de ejecución.|  
    |**Ruta de acceso a los archivos binarios, como ensamblados de TIBCO Rendezvous**|Proporcione esta información si no está ya en la variable de entorno PATH.|  
    |**Conservar orden**|Valor predeterminado es True. Habilita la lógica para enviar mensajes a TIBCO Rendezvous en el mismo orden en el que se han recibido de BizTalk Server. Este parámetro fuerza la publicación en el mismo orden, pero no significa que los suscriptores lo reciban en el mismo orden.|  
    |**Identificador de puerto de envío**|Este identificador aparece en los mensajes de registro asociados a este puerto. Se proporciona como una comodidad.|  
  
4.  Expanda **transporte Rendezvous** y escriba la información de conexión al servidor TIBCO Rendezvous, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
     Se deben establecer los parámetros de conexión para el adaptador de Microsoft BizTalk para TIBCO Rendezvous, para tener acceso a TIBCO Rendezvous.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Demonio**|Valor predeterminado está vacío.<br /><br /> Parámetro del demonio del transporte de Rendezvous.|  
    |**Red**|Valor predeterminado está vacío.<br /><br /> Parámetro de red del transporte de Rendezvous.|  
    |**Servicio**|Valor predeterminado está vacío.<br /><br /> Parámetro de servicio del transporte de Rendezvous.|  
  
5.  Proporcione credenciales mediante el inicio de sesión único (SSO).  
  
     Hay dos métodos que puede utilizar para tener acceso al sistema TIBCO Rendezvous. Puede usar credenciales (parámetros de nombre de usuario y contraseña) o el inicio de sesión único.  
  
    1.  Seleccione **Sí** en el **usar SSO** usar Single Sign-On.  
  
        > [!NOTE]
        >  Vea [seguridad](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) para obtener información acerca de cómo configurar SSO.  
  
    2.  Seleccione una aplicación afiliada de la lista.  
  
         Una aplicación afiliada, creada por la herramientas de Inicio de sesión único empresarial, representa una aplicación como TBCO Rendezvous. El adaptador de Microsoft BizTalk para TIBCO Rendezvous usa las credenciales de un usuario de la aplicación. Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.  
  
        > [!NOTE]
        >  Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications1.md).  
  
6.  Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar** después de proporcionar toda la información necesaria para aceptar la información de conexión.  
  
     Debe establecer parámetros de conexión para el adaptador de BizTalk para TIBCO Rendezvous tener acceso a TIBCO Rendezvous.  
  
## <a name="see-also"></a>Vea también  
 [Creación de controladores de envío de TIBCO Rendezvous](../core/creating-tibco-rendezvous-send-handlers.md)