---
title: Escalar horizontalmente el nivel de servidor SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, MessageBox database
- scaling, scaling out
- SQL Server, scaling
- MessageBox database, scaling
- scaling, strategies
ms.assetid: d5b2ebba-401e-4fde-8818-407fa626043a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 702c253a0135c1dc4af4cea15a9b47c77792586f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272356"
---
# <a name="scaling-out-the-sql-server-tier"></a>Escalar horizontalmente el nivel de SQL Server
Para cada grupo de BizTalk, se agrega una base de datos de cuadro de mensajes principal. Todas las bases de datos de cuadro de mensajes posteriores que se agregan se denominan cuadros de mensajes secundarios. El cuadro de mensajes principal controla todas las suscripciones y el enrutamiento de mensajes. También puede publicar mensajes. Las bases de datos de cuadro de mensajes secundario solo publicarán mensajes cuando estén específicamente configuradas para ello.  
  
## <a name="how-to-add-a-secondary-messagebox-database"></a>Cómo agregar una base de datos de cuadro de mensajes secundario  
 Existen dos maneras de agregar bases de datos de cuadro de mensajes secundario:  
  
-   Agregue la base de datos de cuadro de mensajes secundario al mismo servidor físico.  
  
     Lleve a cabo lo anterior si el servidor físico de cuadro de mensajes existente dispone de recursos de CPU y E/S suficientes y solo se producen en él cuellos de botella por contención de bloqueo. Cree la base de datos de cuadro de mensajes secundario en otras unidades de E/S.  
  
     Ventajas:  
  
    -   El espacio en cabeza adicional de CPU puede utilizarlo otro cuadro de mensajes.  
  
    -   Se necesita un menor número de licencias de SQL Server.  
  
    -   Se elimina el salto de red.  
  
-   Agregue la base de datos de cuadro de mensajes secundaria a un servidor físico diferente.  
  
     En este caso, utilice un servidor físico exclusivo con su propia E/S como base de datos de cuadro de mensajes adicional.  
  
 La ilustración siguiente muestra un escenario donde el nivel de SQL se escala de forma horizontal a tres bases de datos de cuadro de mensajes a partir de una base de datos de cuadro de mensajes.  
  
 ![Escala de MSGBOX](../core/media/scaleoutmsgbox.gif "ScaleOutMSGBOX")  
  
## <a name="when-to-scale-out-the-messagebox-database"></a>Cuándo es recomendable escalar de forma horizontal a una base de datos de cuadro de mensajes  
  
-   En la base de datos de cuadro de mensajes se produce el cuello de botella. Estos cuellos de botella pueden ser:  
  
    -   **CPU** en el caso de escenarios de orquestación muy caros y complejos, la base de datos de cuadro de mensajes consume muchos recursos de CPU. La agregación de otra base de datos de cuadro de mensajes de publicación debería contribuir a incrementar el rendimiento.  
  
    -   **Contención de bloqueo** escenarios complejos formados por varias orquestaciones o instancias de host tienden a crear contenciones de bloqueo en la base de datos de cuadro de mensajes. En este caso, la agregación de otra base de datos de cuadro de mensajes de publicación también debería contribuir a incrementar el rendimiento.  
  
-   El escalamiento vertical no contribuye a solucionar el cuello de botella. Por ejemplo, si la base de datos de cuadro de mensajes principal se encuentra limitada por la contención de bloqueo, el escalamiento horizontal se convierte en la única posibilidad.  
  
-   El escalamiento vertical resulta demasiado caro. Por ejemplo, si actualizar el servidor de cuatro procesadores existente a un servidor en 8 direcciones resulta más caro que agregar otro servidor de cuatro procesadores, el escalamiento horizontal se convierte en la opción más adecuada.  
  
## <a name="when-you-cant-scale-out-the-sql-tier"></a>Cuándo no es recomendable escalar de forma horizontal el nivel de SQL  
 En teoría, el nivel de SQL se debería escalar de forma indefinida siempre que la base de datos de cuadro de mensajes principal no sea el cuello de botella. Para lograrlo, puede convertir la base de datos de cuadro de mensajes principal en una base de datos de no publicación, de manera que solo realice el enrutamiento. No obstante, una vez que el cuadro de mensajes principal contenga un cuello de botella producido por contención de bloqueo, ya no podrá escalar el nivel de SQL de forma horizontal.  
  
## <a name="scale-out-strategies-and-considerations"></a>Estrategias y consideraciones del escalamiento horizontal  
  
-   Realice primero un escalamiento vertical de la base de datos de cuadro de mensajes principal y, a continuación, lleve a cabo el escalamiento horizontal.  
  
-   Escalamiento horizontal de 1 a 3 bases de datos de SQL en lugar de 1 a 2. Tenga en cuenta la 1 topología de SQL server que se muestra en la ilustración anterior titulada "4 BizTalk Server, 1 topología de SQL Server" y da por supuesto que el servidor SQL server está limitada por la CPU, en otras palabras, el procesamiento de la CPU es un cuello de botella. Si agrega solo una base de datos de cuadro de mensajes a esta topología, el cuello de botella aún estará en la CPU y la base de datos de cuadro de mensajes secundario se estará utilizando por debajo de sus posibilidades. Por lo tanto, el factor de escala es casi 1. Si deshabilita la publicación en la base de datos maestra MessageBox y dedicar la base de datos maestra MessageBox solo para el enrutamiento, la base de datos de cuadro de mensajes secundario realizará la publicación. Esto no ayudará a aumentar el rendimiento global, puesto que la base de datos de cuadro de mensajes secundario es el único editor y en ella se produce el cuello de botella. Por consiguiente, la manera más recomendable de realizar el escalamiento horizontal consiste en agregar dos bases de datos de cuadro de mensajes secundario y deshabilitar la publicación en la base de datos de cuadro de mensajes principal.  
  
-   La base de datos de cuadro de mensajes principal formará un cuello de botella en última instancia. Por ello, el equipo físico que aloje la base de datos de cuadro de mensajes principal debe ser más grande y más rápido.  
  
-   Para minimizar el envío de datos a través de la red (y la sobrecarga de DTC consiguiente), considere la posibilidad de colocar varias bases de datos de cuadro de mensajes en el mismo equipo físico con unidades exclusivas. Al mismo tiempo, asegúrese de que en el equipo que contiene las distintas bases de datos no se producen cuellos de botella por estar compartidos los recursos en varias bases de datos de cuadro de mensajes.  
  
-   Todas las bases de datos de cuadro de mensajes secundario deben utilizar hardware similar, pues el trabajo se distribuye de manera uniforme entre las bases de datos de cuadro de mensajes de publicación.  
  
-   Puesto que el escalamiento horizontal de bases de datos de cuadro de mensajes secundario se realiza siempre que no se produzcan cuellos de botella en la base de datos de cuadro de mensajes principal, estas bases de datos de cuadro de mensajes secundario pueden ejecutarse en equipos que posean una CPU con menos recursos que la base de datos de cuadro de mensajes principal.  
  
## <a name="see-also"></a>Vea también  
 [Escalar horizontalmente el nivel de servidor BizTalk Server](../core/scaling-out-the-biztalk-server-tier.md)   
 [Cómo ampliar el nivel de servidor BizTalk Server](../core/scaling-up-the-biztalk-server-tier.md)   
 [Cómo ampliar el nivel de SQL Server](../core/scaling-up-the-sql-server-tier.md)   
 [Hosts de recepción escalados](../core/scaled-out-receiving-hosts.md)   
 [Hosts de procesamiento de escala horizontal](../core/scaled-out-processing-hosts.md)   
 [Hosts de envío de escala horizontal](../core/scaled-out-sending-hosts.md)   
 [Uso de clúster de Windows Server para proporcionar alta disponibilidad para el servidor BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [Bases de datos de escala horizontal](../core/scaled-out-databases.md)   
 [Agrupación en clústeres las bases de datos de servidor BizTalk Server](../core/clustering-the-biztalk-server-databases1.md)