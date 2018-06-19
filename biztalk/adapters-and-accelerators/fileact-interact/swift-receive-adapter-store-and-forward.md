---
title: Adaptador de almacenamiento y reenvío de recepción de SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11eeb335-366b-4b29-9078-de9396b258ca
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 315b9bbe6985bbce5ccb44d8d4846b18730f292b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224476"
---
# <a name="swift-receive-adapter-store-and-forward"></a>Adaptador de almacenamiento y reenvío de recepción de SWIFT
El adaptador de recepción recibe mensajes desde el almacén de SWIFT y reenviar cola (SnF). Para recibir mensajes de la cola, el adaptador debe abrir una sesión con la cola de SnF. Para abrir la cola, debe tener un proceso de cliente dedicado que establece una sesión con la cola. En el diseño, este proceso se implementa como una COM más componente fuera de proceso.  
  
## <a name="push-session-store-and-forward-sequence"></a>Inserción secuencia hacia delante y el almacén de la sesión  
 En la lista siguiente describe el almacén y la secuencia hacia delante.  
  
1.  Inicie la aplicación de servidor que procesa los mensajes.  
  
2.  El proceso de servidor abre los contextos de seguridad necesarios durante la primera SwCallback con el Sw:HandleInitRequest como un primitivo de entrada.  
  
3.  El servidor responde a la Sw:HandleInitRequest con uno o ambos Sw:CryptoMode y Sw:FACryptoMode establecido en Opciones avanzadas.  
  
     El servidor ahora está listo para empezar a procesar las solicitudes entrantes.  
  
4.  Para iniciar la entrega de mensajes de una cola, un proceso de cliente inicia una sesión de inserción. En función de la configuración del adaptador (modo de inserción), el adaptador de recepción genera un proceso de cliente llamado a SnFQueueManager.exe para adquirir la cola en modo de inserción.  
  
5.  Un SwCall() se ejecuta con Sw:AcquireSnFRequest (dentro de la Sw:ExchangeSnFRequest) como un primitivo de entrada. Esta solicitud, inicia una sesión con la cola indicada (si el SwSec:AuthorisationContext tiene el rol RBAC necesarios).  
  
6.  Inmediatamente después de responder con "Aceptado" en el Sw:AcquireStatus, SWIFTNet SnF comienza a enviar mensajes al servidor de acuerdo con lo especificado en la adquisición. Si el adaptador de recepción no se ha iniciado, los mensajes lleguen a las excepciones. (Que es por eso es importante contar con los adaptadores de recepción que se ha iniciado).  
  
7.  SWIFTNet SnF inicia e inserta un número de mensajes (hasta el tamaño de la ventana).  
  
8.  Para cada mensaje que se confirma, se inserta un nuevo mensaje (si existe).  
  
9. El proceso de cliente (SnFQueueManager.exe) ha terminado su trabajo y puede finalizar ahora. El proceso emite SwSec:DestroyContextRequest, que limpia los contextos de seguridad abierta. Después de la Sw:TermRequest, el proceso se cierra.  
  
### <a name="message-correlation"></a>Correlación de mensajes  
 El campo RequestRef se conservan y se sustituye en los mensajes de respuesta por el adaptador de recepción. Esto garantiza la correlación de extremo a extremo entre el mensaje entrante y el mensaje de respuesta  
  
### <a name="duplicate-processing"></a>Procesamiento duplicado  
 Si recibe una solicitud de FileAct y la instancia de adaptador recibe un mensaje con un nodo de indicador posibles duplicados, a continuación, debe comprobar si la transferencia que se hace referencia ya se ha completado correctamente o si ha producido un error y realice la acción apropiada. Si la transferencia de archivos ya ha llevado a cabo, a continuación, el adaptador actualiza el estado de la transferencia como "Duplicate" en caso contrario, actualiza como "Aceptado".  
  
### <a name="acknowledgments"></a>Confirmaciones  
 Si el remitente solicita una confirmación de una solicitud de FileAct, el adaptador comprueba si el evento de finalización de la transferencia de archivos y genera la confirmación después de comprobar el valor de resumen de archivo. El adaptador envía el mensaje de confirmación a BizTalk para el adaptador de envío recogerlo y enviarlo al remitente.  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)   
 [URI del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)   
 [La inicialización del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)   
 [Contexto de seguridad del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)   
 [Modos sincrónico y diferido del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)