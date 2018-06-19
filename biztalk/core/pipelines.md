---
title: Las canalizaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines
- deploying, pipelines
- receive pipelines, about receive pipelines
- pipelines, deploying
- send pipelines, about send pipelines
- receive pipelines
- pipelines, about pipelines
- send pipelines, stages
- send pipelines
- pipelines, receive pipelines
- pipelines, send pipelines
- receive pipelines, stages
ms.assetid: 76947dd8-728a-4fa3-bd33-7a708ae82cac
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5fec49dcc9ba21c5d117188f280f7e9b65fe2b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265276"
---
# <a name="pipelines"></a>Canalizaciones
Las canalizaciones son un componente de Microsoft BizTalk Server que proporciona una implementación del patrón de integración de canalizaciones y filtros. Durante la recepción y el envío de mensajes, existen motivos empresariales para realizar transformaciones en los mensajes para prepararlos para entrar o salir de BizTalk Server.  
  
 Un ejemplo común es que podría necesitar transformar un archivo sin formato delimitado por comas en un archivo XML a fin de beneficiarse de algunas características de BizTalk Server como las asignaciones. El componente desensamblador de archivos sin formato hace exactamente esto. Es habitual en casos de integración que sea necesario realizar varios tipos de transformaciones en un mensaje antes de recibirlo o enviarlo. Las canalizaciones se utilizan para cumplir con este requisito. Las canalizaciones permiten al programador definir una serie de transformaciones que se realizarán en un mensaje al recibirlo o enviarlo.  
  
 Existen dos tipos de canalizaciones, de envío y recepción, y éstas coinciden con los puertos en los que se ejecutan. *Canalizaciones de envío* se ejecutan en puertos de envío y puerto de recepción en la parte de la respuesta de una solicitud/respuesta mientras *canalizaciones de recepción* se ejecutan en ubicaciones de recepción y en la parte de la respuesta de una petición-respuesta puerto de envío. En esencia, las canalizaciones de recepción tienen como finalidad transformar los mensajes que se están publicando en la base de datos de cuadro de mensajes, mientras que las canalizaciones de envío tienen como finalidad usarse en mensajes que se han suscrito y se están enviando fuera de BizTalk Server.  
  
 Cada canalización tiene un conjunto de fases que se ejecutan por orden al ejecutar la canalización. Cada fase puede incluir cero o más componentes. El número máximo de componentes depende de la fase.  
  
## <a name="receive-pipeline-stages"></a>Fases de la canalización de recepción  
 ![Etapas de canalización de recepción](../core/media/arch-pipe-receive.gif "arch_pipe_receive")  
  
|Fase|Finalidad|  
|-----------|-------------|  
|**Descodificar**|Descifra o descodifica los datos del mensaje.|  
|**Desensamblar**|Desensambla un intercambio en mensajes más pequeños y analiza el contenido de los mensajes.|  
|**Validar**|Valida los datos de mensajes, normalmente con un esquema.|  
|**Resolver entidad**|Identifica la entidad del servidor BizTalk Server asociada con algún token de seguridad en el mensaje o el contexto del mensaje.|  
  
## <a name="send-pipeline-stages"></a>Etapas de canalización de envío  
 ![Etapas de canalización de envío](../core/media/arch-pipe-send.gif "arch_pipe_send")  
  
|Fase|Finalidad|  
|-----------|-------------|  
|**Preensamblar**|Realiza cualquier procesamiento de mensajes necesario antes de ensamblar el mensaje.|  
|**Ensamblar**|Ensambla el mensaje y lo prepara para su transmisión realizando pasos como agregar sobres, convertir archivos XML en archivos sin formato o cualquier otra tarea complementaria a la fase de desensamblado en una canalización de recepción.|  
|**Codificar**|Codifica o cifra el mensaje antes de la entrega.|  
  
 Una fase de una canalización tiene un *modo de ejecución* de todo o primera coincidencia, que controla los componentes que se ejecutan si se agrega más de un componente a una fase. Para las fases con el modo Todo, se llama a cada componente para procesar el mensaje en el orden en el que se han configurado en la fase. Si el modo es Primera coincidencia, se sondea cada componente para indicar que es el componente correcto hasta que se encuentre una coincidencia, en cuyo momento se ejecuta el componente coincidente, mientras que los demás componentes no se ejecutan.  
  
 Como ejemplo de los modos de ejecución, la fase Desensamblar de una canalización de recepción es una fase Primera coincidencia. Por lo tanto, se llama a cada componente de la fase para ver si reconoce el mensaje y puede procesarlo. Si el componente responde de forma afirmativa, no se consultará a ningún otro componente de la fase para ver si también puede controlar el mensaje. No obstante, la fase Descodificar de una canalización de recepción tiene el modo de ejecución Todo, lo que significa que se llama a cada componente de esta fase para procesar el mensaje en el orden en el que se ha configurado. El primer descodificador podría descifrar el mensaje, mientras que el segundo podría descomprimir el mensaje desde un formato comprimido.  
  
 Una consecuencia común del modo de ejecución en el procesamiento de canalizaciones se produce cuando un programador desea utilizar varios desensambladores en una sola canalización de recepción. Con frecuencia, los componentes de desensamblado difieren solo ligeramente. Por ejemplo, dos desensambladores con esquemas configurados similares pero diferentes. En este caso, mientras que el mensaje podría coincidir realmente con el esquema definido en el segundo desensamblador, el primer desensamblador podría determinar mediante su búsqueda que puede procesar el mensaje. Solo después de procesar el mensaje, se descubre el error y se suspende el mensaje. En estos casos, puede crear un desensamblador nuevo que tenga una lógica de búsqueda más específica o crear dos canalizaciones diferentes y recibir los distintos mensajes en ubicaciones de recepción diferentes.  
  
## <a name="pipeline-deployment"></a>Implementar canalizaciones  
 Al implementar un ensamblando que contiene una canalización, la base de datos de administración guarda la canalización. La canalización se asocia con la versión específica del ensamblado con los siguientes resultados:  
  
-   Si implementa varios ensamblados que utilicen la misma canalización, la base de datos de administración crea una entrada para la canalización para cada ensamblado.  
  
-   Al quitar un ensamblando que contiene una canalización, la base de datos de administración quita la canalización que está asociada con el ensamblado. Puesto que hay una copia de la canalización para cada ensamblado asociado en la base de datos de administración, quitar un ensamblado no afecta a los demás.  
  
## <a name="see-also"></a>Vea también  
 [Artefactos](../core/artifacts.md)