---
title: "¿Qué es el adaptador de FileAct? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05ec8f1e-57f9-4e2d-ab8b-22b5c4b28055
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62b83fc723bbebce857eb442384b14179c1072ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-fileact-adapter"></a>¿Qué es el adaptador de FileAct?
El adaptador de FileAct para SWIFTNet proporciona conectividad entre BizTalk Server y la sociedad para red de IP de seguros de telecomunicaciones financieros bancos vinculados (SWIFT) en todo el mundo (SIPN) para la transferencia de archivos. La SIPN transfiere archivos y mensajes a través de una red privada segura que conecta las instituciones financieras, infraestructuras de sector financiero y los clientes. El adaptador de FileAct utiliza la interfaz de programación de aplicaciones (API) s para conectarse a la SIPN SWIFTNet vínculo (SNL).  
  
 El adaptador de FileAct proporciona un mecanismo para SWIFT a participantes de forma segura y confiable intercambiar archivos y la información relativa a esos archivos. Admite la funcionalidad siguiente:  
  
-   Enviar archivos a un usuario SWIFTNet  
  
-   Recuperar archivos de un usuario SWIFTNet  
  
-   Para confirmar la recepción de archivo por un destinatario de notificación de entrega  
  
-   Anulación de las transferencias en curso  
  
-   Supervisión de estado de transferencia de archivos  
  
-   Transferencias de archivos simultáneas  
  
-   Garantía de autenticidad de los datos y de integridad  
  
-   Confidencialidad de los datos de archivo en tránsito  
  
-   Sin rechazo de las transferencias de archivos  
  
-   Marca de tiempo  
  
## <a name="the-fileact-service"></a>El servicio de FileAct  
 El adaptador de FileAct para SWIFTNet proporciona a una transferencia segura y confiable de archivos, como lotes de mensajes estructurados de financieros o informes de gran tamaño. Las aplicaciones típicas incluyen las transferencias de crédito repetitivos como pensión o pagos de salario, información de valor añadido de títulos y elaboración de informes y legales. SWIFTNet FileAct ofrece una variedad de modos de mensajes:  
  
-   **Transferencia de archivos de almacenamiento y reenvío.** Capacidad de almacenamiento y reenvío de SWIFTNet FileAct quita la incertidumbre y los inconvenientes de tener que preocuparse de si son o no sus correspondientes en línea en el momento de que transmitir el archivo. El archivo se entregará tan pronto como el destinatario está listo para recibirlo. Como resultado, proporciona una forma ideal de enviar archivos a un gran número de correspondientes, algunos de los cuales pueden ser en zonas horarias diferentes.  
  
-   **Transferencia de archivos en tiempo real.** Mensajería en tiempo real ofrece una alternativa de bajo costo para almacenar y reenviar para los archivos que están destinados a correspondientes que están en línea en el momento de la transmisión. Como resultado es ideal para enviar archivos a unos correspondientes grandes o infraestructuras de mercado.  
  
-   **Recuperación de archivos en tiempo real.** Se trata de un servicio interactivo que se utiliza normalmente para recuperar los archivos en el contexto de los sistemas basados en la estación de trabajo y a menudo junto con SWIFTNet Examinar. Se admite este modo.  
  
 Las características de SWIFTNet FileAct opcionales (en forma de archivo por archivo) se incluyen:  
  
-   **Prioridad del mensaje.** Las transferencias de archivos se pueden marcar como "Urgente" en el mensaje, para permitir adecuado de procesamiento por sus correspondientes.  
  
-   **Notificación de entrega (modos de almacenamiento y reenvío y en tiempo real).** Proporciona la confirmación de que el destinatario recibe el archivo.  
  
-   **Sin rechazo de recepción y de emisión.** En caso de conflicto, permite SWIFT confirmar que la transferencia de archivos tuvo lugar como reclamado.  
  
 Las características de SWIFTNet FileAct estándares incluyen seguridad SWIFTNet PKI**.** SWIFTNet FileAct se protege con SWIFTNet PKI y ofrece control de integridad y autenticación de mensajes.  
  
 Todos los mensajes y archivos intercambiados en SWIFTNet debe someterse a un conjunto común de comprobaciones para asegurarse de que ningún usuario puede omitir la seguridad, validación y las reglas de enrutamiento de la plataforma. Estas comprobaciones se realizan mediante la aplicación de puerta de enlace de SWIFTAlliance (SAG).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la FileAct e interactuar adaptadores](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [¿Qué es SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [¿Qué es el adaptador de interactuar?](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)