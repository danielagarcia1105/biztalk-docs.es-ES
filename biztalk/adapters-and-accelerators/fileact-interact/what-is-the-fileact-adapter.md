---
title: ¿Qué es el adaptador de FileAct? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05ec8f1e-57f9-4e2d-ab8b-22b5c4b28055
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc6fe9b28e4ea2b5eee087b61866827a766c3e3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971493"
---
# <a name="what-is-the-fileact-adapter"></a>¿Qué es el adaptador de FileAct?
El adaptador de FileAct para SWIFTNet proporciona conectividad entre BizTalk Server y la sociedad de telecomunicaciones financieros entre bancos más (SWIFT) en todo el mundo Secure IP red (SIPN) para la transferencia de archivos. La SIPN transfiere archivos y mensajes a través de una red privada segura que se conecta a las instituciones financieras, infraestructuras de la industria financiera y clientes. El adaptador de FileAct utiliza la interfaz de programación de aplicaciones (API) s para conectarse a la SIPN SWIFTNet vínculo (SNL).  
  
 El adaptador de FileAct proporciona un mecanismo para SWIFT participantes de forma segura y confiable intercambiar archivos y la información relativa a esos archivos. Admite la funcionalidad siguiente:  
  
-   Enviar archivos a un usuario de SWIFTNet  
  
-   Recuperación de archivos de un usuario de SWIFTNet  
  
-   Para confirmar la recepción de archivo por un receptor de notificación de entrega  
  
-   Anulación de transferencias en curso  
  
-   Supervisión de estado de transferencia de los archivos  
  
-   Transferencias de archivos simultáneas  
  
-   Garantía de integridad y autenticidad de los datos  
  
-   Confidencialidad de los archivos de datos en tránsito  
  
-   Sin repudio de transferencias de archivos  
  
-   Marca de tiempo  
  
## <a name="the-fileact-service"></a>El servicio de FileAct  
 El adaptador de FileAct para SWIFTNet proporciona a transferencia segura y confiable de archivos, como lotes de mensajes estructurados de financieros o informes de gran tamaño. Las aplicaciones típicas incluyen transferencias repetitivos como pensiones o los pagos del salario, información de valor añadido de títulos y elaboración de informes y las disposiciones legales. SWIFTNet FileAct ofrece una variedad de modos de mensajes:  
  
- **Transferencia de archivos de Store y reenvío.** Capacidad de almacenamiento y reenvío de SWIFTNet FileAct elimina la incertidumbre y los inconvenientes de tener que preocuparse de si son o no los corresponsales en línea en el momento de que transmitir el archivo. El archivo se entregará tan pronto como el destinatario está listo para recibirlo. Como resultado, proporciona una forma ideal de enviar archivos a un gran número de corresponsales, algunos de los cuales pueden estar en distintas zonas horarias.  
  
- **Transferencia de archivos en tiempo real.** Mensajería en tiempo real, ofrece una alternativa de menor costo para almacenar y reenviar para los archivos que están destinados a corresponsales que están en línea en el momento de la transmisión. Como resultado es ideal para enviar archivos a unos corresponsales grandes o infraestructuras de mercado.  
  
- **Recuperación de archivos en tiempo real.** Se trata de un servicio interactivo que se utiliza normalmente para recuperar archivos en el contexto de los sistemas basados en la estación de trabajo y a menudo junto con SWIFTNet Examinar. Admitimos este modo.  
  
  Las características opcionales de SWIFTNet FileAct (dentro de un archivo por archivo) se incluyen:  
  
- **Prioridad del mensaje.** Las transferencias de archivos pueden marcarse como "Urgente" en el mensaje, para permitir adecuado de procesamiento por sus corresponsales.  
  
- **Notificación de entrega (modos en tiempo real y de almacenamiento y reenvío).** Proporciona la confirmación de que el destinatario recibe el archivo.  
  
- **Sin repudio de recepción y de emisión.** En el caso de conflicto, permite SWIFT confirmar que la transferencia de archivos tuvo lugar como reclamado.  
  
  Las características de SWIFTNet FileAct estándares incluyen seguridad SWIFTNet PKI<strong>.</strong> SWIFTNet FileAct está protegida con SWIFTNet PKI y ofrece control de integridad y autenticación de mensajes.  
  
  Todos los mensajes y los archivos que se intercambian en SWIFTNet someterse a un conjunto común de comprobaciones para asegurarse de que ningún usuario puede omitir la seguridad, validación y las reglas de enrutamiento de la plataforma. Estas comprobaciones se realizan mediante la aplicación de puerta de enlace SWIFTAlliance (SAG).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la FileAct e interactuar de adaptadores](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [¿Qué es SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [¿Qué es el adaptador de InterAct?](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)