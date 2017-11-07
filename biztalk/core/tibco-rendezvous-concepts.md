---
title: Conceptos de TIBCO Rendezvous | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36060091-57dc-4125-8dca-23058d813deb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9969ff652791e551f8603c0ec890704bccb12c37
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-rendezvous-concepts"></a>Conceptos de TIBCO Rendezvous

## <a name="concepts-explained"></a>Conceptos explicados
En la siguiente tabla se describen algunas de las características y conceptos de TIBCO Rendezvous.  
  
|Concepto|Definición|  
|-------------|----------------|  
|**Mensajes**|Transportan datos entre procesos o subprocesos de programas. Los mensajes contienen campos de datos autodescriptivos. Los programas pueden manipular campos del mensaje, enviar mensajes y recibir mensajes.|  
|**Eventos**|Crean objetos de evento para registrar interés en condiciones importantes. Por ejemplo, distribuir un evento de escucha notifica al programa que ha llegado un mensaje y distribuir un evento de temporizador notifica al programa que su intervalo ha transcurrido.<br /><br /> Los programas definen las funciones de devolución de llamada de evento para procesar eventos.|  
|**Asuntos**|Los mensajes están asociados con un nombre lógico (asunto). Los programas escuchan un asunto determinado o publican mensajes bajo un asunto específico.|  
|**Transportes**|Objetos que definen el ámbito, el mecanismo y los protocolos de la entrega.|  
|**Modo por lotes**|Los objetos de transporte de TIBCO Rendezvous admiten un modo por lotes para la publicación de mensajes. <br />Modo predeterminado es: enviar mensajes tan pronto como sea posible. Modo de temporizador es: acumular mensajes y enviarlos al búfer está lleno o caduque el intervalo del temporizador.|  
|**Cola**|Los programas crean colas de eventos para organizar los eventos. Una cola contiene una secuencia de objetos de evento que están listos para ser procesados.|  
|**Grupo de cola**|Personaliza el procesamiento de eventos mediante la combinación de las colas (con diferentes prioridades).|  
|**Entrega de mensajes certificados**|Confirma la entrega de cada mensaje a cada destinatario registrado. Entrega mensajes a pesar de la terminación y reinicio del proceso usando la contabilidad basada en archivos.<br /><br /> La entrega certificada asegura a los programas que cada mensaje certificado llega a cada destinatario, en el orden en que se envía. Si no es posible la entrega, tanto el programa de envío como el de escucha reciben información explícita acerca del mensaje no entregado.<br /><br /> Los programas determinan un límite de tiempo explícito para cada mensaje.<br /><br /> Una vez que un programa envía un mensaje certificado, el software de TIBCO Rendezvous continúa los intentos de entrega hasta que tiene éxito o hasta que finaliza el límite de tiempo del mensaje.<br /><br /> El software de entrega certificada de TIBCO Rendezvous presenta mensajes de aviso para informar a los programas de cada evento significativo relacionado con la entrega.<br /><br /> El software de entrega certificada de TIBCO Rendezvous registra el estado de cada mensaje en una contabilidad. Los programas que requieren certificación solo durante el proceso del programa deben usar una contabilidad basada en procesos. Los programas que requieren una certificación que transcienda la terminación del proceso y reinicio del programa usan una contabilidad basada en archivo.<br /><br /> Si no se permite la entrega certificada, las condiciones de entrega se reducen a la semántica de entrega fiable de TIBCO Rendezvous estándar.|  
|**Daemons de cola distribuida**|Distribuyen un servicio a través de varios procesos.<br /><br /> El daemon de TIBCO Rendezvous completa la ruta informativa entre los procesos de programa de TIBCO Rendezvous a lo largo de la red. Los programas intentan conectarse a un proceso de daemon de TIBCO Rendezvous. Si un proceso de daemon local aún no está en ejecución, el programa comienza uno automáticamente y se conecta a él. El daemon TIBCO Rendezvous organiza los detalles de transporte de datos, solicitud de paquetes, confirmación de recepción, solicitudes de retransmisión y distribución de información a los procesos de programa correctos. El daemon oculta todos estos detalles de los programas de TIBCO Rendezvous. El daemon de TIBCO Rendezvous es casi invisible para los programas que dependen de él. Los programas envían y reciben información usando las llamadas de comunicación de TIBCO Rendezvous y el daemon de TIBCO Rendezvous realiza el trabajo de llevar información al lugar adecuado.<br /><br /> El daemon realiza lo siguiente:<br /><br /> -Transmite mensajes de salida de procesos de programa a la red.<br />-Proporciona mensajes de la red a los procesos de programa de entrada.<br />-Filtra los mensajes dirigidos al asunto.<br />-Protege los programas de idiosincrasias del sistema operativo, por ejemplo, sockets de bajo nivel.|  
|**Seguridad**|TIBCO Rendezvous admite la autenticación basada en certificados o (usuario, contraseña).|  
|**Circuitos virtuales**|Cuentan con la comunicación de Rendezvous entre dos terminales a través de una conexión exclusiva y continua supervisada.|  
|**Comunicación directa**|Comunicaciones punto a punto sin procesos daemon intermediarios de Rendezvous.|  
  
## <a name="see-also"></a>Vea también  
 [Mensajes en el adaptador de BizTalk para TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md)   
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)