---
title: Mensajes de procesamiento de varias partes con el adaptador de POP3 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56ad041f-f155-4c1c-ab87-1405c80d9b68
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26aff4569414103ad8c4f37a9e4699a85874e481
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266444"
---
# <a name="processing-multi-part-messages-with-the-pop3-adapter"></a>Procesar mensajes de varias partes con el adaptador de POP3
El adaptador de POP3 puede procesar mensajes codificado con MIME que cumplen con los estándares IETF documentados en [RFC 2045](http://go.microsoft.com/fwlink/?LinkId=58810), [RFC 2046](http://go.microsoft.com/fwlink/?LinkId=58811), y [RFC 2047](http://go.microsoft.com/fwlink/?LinkId=58812). Los mensajes codificados con MIME pueden tener una o varias partes con distintos tipos de contenido. En este tema se trata el modo en que el adaptador de POP3 procesa mensajes de varias partes codificados con MIME.  
  
## <a name="receiving-multi-part-messages-with-the-pop3-adapter"></a>Recibir mensajes de varias partes con el adaptador de POP3  
 Si tiene una ubicación de recepción que usa el adaptador de POP3 el **aplicar descodificación MIME** opción establecida en **True** , a continuación, el adaptador de POP3 lleva a cabo las siguientes acciones al recibir un mensaje codificado con MIME:  
  
1.  Crea un mensaje de BizTalk de varias partes a partir de las partes del mensaje codificado con MIME que recibe. Este mensaje de varias partes puede contener 1 o varias partes y tendrá el mismo número de partes que el mensaje codificado con MIME recibido.  
  
2.  Detecta los encabezados del mensaje codificado con MIME. Si los encabezados coinciden con la lista de propiedades que se documentan en el tema [propiedades y esquema de propiedades de adaptador de POP3](../core/pop3-adapter-property-schema-and-properties.md) , a continuación, estos encabezados se promocionan al mensaje de BizTalk de varias partes como propiedades de contexto.  
  
3.  Usa un algoritmo configurable para designar una de las partes del mensaje codificado con MIME como parte del cuerpo del mensaje de BizTalk. El algoritmo utilizado para determinar qué parte del mensaje será la parte del cuerpo de mensaje de BizTalk se describe a continuación en la sección **cuerpo parte selección algoritmo utilizado por el adaptador de POP3**.  
  
4.  Publica el mensaje de BizTalk de varias partes en el cuadro de mensajes.  
  
## <a name="body-part-selection-algorithm-used-by-the-pop3-adapter"></a>Algoritmo de selección de parte del cuerpo usado por el adaptador de POP3  
 Cuando el adaptador de POP3 crea un mensaje de BizTalk de varias partes a partir de las partes del mensaje codificado con MIME recibido, se selecciona una de las partes del mensaje como parte del cuerpo del mensaje de BizTalk. La parte del cuerpo del mensaje de BizTalk la usa BizTalk Server para la validación del mensaje, asignación, promoción de propiedades, ensamblado de archivo sin formato y otras operaciones. Los suscriptores a un mensaje de BizTalk de varias partes reciben todas las partes del mensaje pero sólo consumirán la parte designada del cuerpo del mensaje de BizTalk a menos que utilicen una orquestación, una canalización personalizada o un adaptador que pueda comprender mensajes de varias partes. Por ejemplo, puede configurar una orquestación para leer todas las partes de un mensaje de varias partes; el adaptador de SMTP puede leer todas las partes de un mensaje de varias partes y se puede configurar una canalización personalizada para usar el componente de canalización de codificador de MIME/SMIME. Para obtener más información sobre el uso de una orquestación para consumir un mensaje de varias partes, vea la sección siguiente, **de procesamiento de mensajes de varias partes en orquestaciones**.  
  
 El adaptador de POP3 selecciona la parte del cuerpo de mensaje de BizTalk de las partes del cuerpo disponibles en función de los valores suministrados para la **índice de parte del cuerpo** y **tipo de contenido de parte de cuerpo**.  
  
> [!NOTE]
>  El adaptador de POP3 está diseñado para reconocer los tipos de contenido de parte de cuerpo que se definen en [RFC 2046](http://go.microsoft.com/fwlink/?LinkId=119569).  
  
 El algoritmo que se usa para seleccionar la parte del cuerpo del mensaje de BizTalk de un correo electrónico se describe a continuación:  
  
1.  Si el **índice de parte del cuerpo** se establece en 0 y el **tipo de contenido de parte de cuerpo** está en blanco, a continuación, se utiliza el siguiente algoritmo para seleccionar la parte del cuerpo de mensaje de BizTalk:  
  
    -   Use la primera parte MIME con el encabezado de descripción de contenido establecido como "cuerpo".  
  
    -   De lo contrario, use la primera parte MIME con el encabezado de tipo de contenido establecido como "texto/xml".  
  
    -   De lo contrario, use la primera parte MIME con el encabezado de tipo de contenido establecido como "texto/sin formato".  
  
    -   En caso contrario, utilice la primera parte MIME con el encabezado Content-Type establecido en "texto /".  
  
    -   O bien, utilice la primera parte MIME.  
  
2.  En caso contrario si el **índice de parte del cuerpo** se establece en 0 y el **tipo de contenido de parte de cuerpo** , entonces la primera parte del cuerpo del mensaje entrante que coincida con lo especificado **tipo de contenido de parte de cuerpo** se selecciona como parte del cuerpo del mensaje de BizTalk. Si no hay partes con un tipo de contenido coincidente, el mensaje se suspende.  
  
3.  En caso contrario si el **índice de parte del cuerpo** se establece en un valor mayor que 0 y el **tipo de contenido de parte de cuerpo** está en blanco, a continuación, se selecciona la parte del cuerpo con el índice especificado como parte del cuerpo del mensaje de BizTalk. Si el índice especificado es mayor que el número de partes del cuerpo, el mensaje se suspende.  
  
4.  Lo contrario si el **índice de parte del cuerpo** se establece en un valor mayor que 0 y el **tipo de contenido de parte de cuerpo** está establecida, la **índice de parte del cuerpo** solo se aplica cuerpo a las partes que coinciden con la cadena **tipo de contenido de parte de cuerpo** y la parte del cuerpo correspondiente se selecciona como parte del cuerpo del mensaje de BizTalk. Si el índice especificado es mayor que el número de partes con un tipo de contenido coincidente, el mensaje se suspende. Si no hay partes con un tipo de contenido coincidente, el mensaje se suspende.  
  
5.  La parte que se selecciona como parte del cuerpo del mensaje de BizTalk se convierte en la primera parte del mensaje de BizTalk de varias partes que se publica en el cuadro de mensajes, las partes restantes del mensaje conservan el orden que tenían en el mensaje original codificado con MIME.  
  
## <a name="processing-multi-part-messages-in-orchestrations"></a>Procesar mensajes de varias partes en orquestaciones  
 Si el adaptador de POP3 crea un mensaje de BizTalk de varias partes a partir del mensaje codificado con MIME recibido, todas las partes se publican en la base de datos de cuadro de mensajes aunque sólo se designe una de las partes como parte del cuerpo del mensaje de BizTalk. Por consiguiente, una orquestación suscrita al mensaje de varias partes consume una orquestación. En esta sección se documentan algunas consideraciones al procesar mensajes de varias partes en una orquestación.  
  
### <a name="processing-multi-part-messages-with-a-known-number-of-parts-and-known-part-types"></a>Procesar mensajes de varias partes con un número de partes y tipos de partes conocidos  
 Si la orquestación recibe un mensaje de varias partes con un número de partes y tipos de partes conocidos, puede declarar un mensaje de varias partes en la orquestación y establecer el número de partes y tipos de partes en tiempo de diseño.  
  
### <a name="processing-multi-part-messages-with-unknown-part-types"></a>Procesar mensajes de varias partes con tipos de partes desconocidos  
 Si la orquestación recibe un mensaje de varias partes con tipos de partes desconocidos, a continuación, puede declarar un mensaje de varias partes en la orquestación y utilizar el **XmlDocument** tipo para cada uno de los elementos para los que el tipo es desconocido.  
  
### <a name="processing-multi-part-messages-with-an-unknown-number-of-parts-and-all-of-the-part-types-are-unknown"></a>Procesar mensajes de varias partes con un número y todos los tipos de partes desconocidos  
 Si la orquestación recibe un mensaje de varias partes con un número desconocido de partes, a continuación, puede declarar un mensaje de varias partes con una única parte de la **XmlDocument** tipo en la orquestación para recibir el mensaje. Si se recibe un mensaje de varias partes que contiene mayor que el número de partes declarados, las lecturas de motor de orquestación están cuántos elementos hay en el mensaje, a continuación, crea los tipos de partes apropiados para los elementos que coinciden con el número de partes del mensaje declarado tipo y, a continuación, las construcciones **XmlDocument** partes de las partes restantes.