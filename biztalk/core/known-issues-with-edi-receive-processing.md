---
title: Conoce problemas con EDI de procesamiento de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbb3fd6a-381b-479e-a9f2-7b6371fac39e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ab2769ab4a6eacf885dbf675a6bd3fda371007
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262964"
---
# <a name="known-issues-with-edi-receive-processing"></a>Problemas conocidos del procesamiento de recepción de EDI
En este tema se describen los problemas conocidos del procesamiento en la canalización de recepción EDI.  
  
## <a name="receive-side-processing-of-trailing-separators-fails"></a>Se producen errores en el procesamiento de recepción de los separadores finales.  
 **Síntoma**  
  
 Se producen errores en un conjunto de transacciones con un separador final; el código de error es AK403= 6 para un mensaje con codificación X12 o los códigos UCM3=4/UCD1=45 para un mensaje con codificación EDIFACT.  
  
 **Causa posible**  
  
 El procesamiento de los separadores finales no está habilitado.  
  
 **Resolución**  
  
 Abra el cuadro de diálogo Propiedades de EDI correspondientes a la entidad que ha enviado el mensaje. En la página de validación y generación de confirmación del cuadro de diálogo Propiedades de EDI (tanto para X12 como para EDIFACT), seleccione la opción que permite los delimitadores o separadores finales. Después de seleccionar esta casilla de verificación, puede especificar la creación de etiquetas XML para separadores finales en el XML intermedio seleccionando la opción "Crear etiquetas XML vacías para los separadores finales".  
  
## <a name="contrl-ack-is-enabled-but-not-generated"></a>La confirmación CONTRL está habilitada, pero no se ha generado.  
 **Síntoma**  
  
 La casilla para generar confirmación funcional de la página de validación y generación de confirmación correspondiente a la entidad de envío está activada, pero la canalización de recepción EDI no ha generado ninguna confirmación CONTRL.  
  
 **Causa posible**  
  
 El mensaje CONTRL contiene varios elementos de datos obligatorios que se deben copiar del intercambio. Si falta el elemento de datos del intercambio o no es válido sintácticamente, la canalización de recepción no puede generar un mensaje CONTRL válido en lo que respecta a la sintaxis.  
  
 **Resolución**  
  
 Informe del error usando otros medios distintos a la confirmación CONTRL.  
  
## <a name="there-was-a-failure-executing-the-receive-pipeline-error-message"></a>"Se produjo un error al ejecutar la canalización de recepción …" Mensaje de error  
 **Síntoma**  
  
 El intento de ejecución de una canalización de recepción AS2 genera un error 80040154.  
  
 **Causa posible**  
  
 Las instancias de host de 64 bits no admiten canalizaciones.  
  
 **Resolución**  
  
 Asocie la canalización a un host de 32 bits.  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a>Un mensaje con codificación X12 se suspende si la autenticación basada en puerto está habilitada y BizTalk Server no dispone de acceso a la información de autorización y seguridad.  
 **Síntoma**  
  
 Cuando se recibe un mensaje a través de un puerto de recepción para el que está habilitada la autenticación y la entidad que ha enviado el mensaje no puede determinarse, BizTalk Server suspenderá el mensaje.  
  
 **Causa posible**  
  
 Si la autenticación está habilitada para un puerto de recepción (la propiedad "Sin autenticación" del puerto de recepción está desactivada), BizTalk Server necesita la configuración de las propiedades "Calificador de autorización (ISA1) e Información (ISA2)" y "Calificador de seguridad (ISA3) e Información (ISA4)" para procesar el intercambio. Estas propiedades están establecidas para una entidad en la página Propiedades de procesamiento de intercambio X12 de la entidad como remitente de intercambio. Si BizTalk Server no puede determinar los valores de estas propiedades, suspenderá el mensaje.  
  
 Esto puede ocurrir de dos maneras. En el primer caso, si BizTalk Server no puede determinar la entidad que ha enviado el mensaje, utilizará las propiedades globales de EDI y no dispondrá de acceso a la configuración de seguridad y autorización. Como resultado, suspenderá el mensaje. En el segundo caso, si BizTalk Server determina la entidad, pero las propiedades ISA1-2 e ISA3-4 de la entidad no están configuradas, BizTalk Server seguirá sin disponer de acceso a la información de seguridad y autorización y suspenderá el mensaje.  
  
 **Resolución**  
  
 Asegúrese de que la entidad de envío del mensaje puede identificarse y de que las propiedades ISA1-2 e ISA3-4 están definidas en el acuerdo de la entidad.  
  
## <a name="incorrect-se01-in-a-split-hipaa-subdocument"></a>SE01 incorrecto en un subdocumento HIPAA de división  
 **Síntoma**  
  
 El finalizador de conjunto de transacciones (campo SE01) proporciona un recuento de segmentos de datos, incluidos los segmentos de encabezado y finalizador de un documento X12/HIPAA. Sin embargo, para un subdocumento HIPAA de división, la canalización de recepción de EDI aplica el mismo valor SE01 que el documento original, en lugar de volverlo a calcularlo.  
  
 **Causa**  
  
 La canalización de recepción de EDI copia el valor de SE01 del documento HIPAA original en un subdocumento de división.  
  
## <a name="error-message-for-duplicate-unb5-or-unh1-is-not-descriptive"></a>El mensaje de error de UNB5 o UNH1 duplicados no es descriptivo.  
 Si el servidor BizTalk Server recibe un mensaje con un número de control de intercambio (UNB5) o un número de referencia del conjunto de transacciones (UNH1) duplicados, el código de error y la descripción que envía no indicarán con claridad la naturaleza del problema.  
  
## <a name="biztalk-server-will-suspend-a-very-large-interchange-if-it-runs-out-of-memory"></a>BizTalk Server suspenderá un intercambio muy largo si se queda sin memoria.  
 BizTalk Server puede quedarse sin memoria cuando analiza un intercambio muy largo. En ese caso, enviará un error y suspenderá el intercambio. En la página Concentrador de grupo, no podrá ver el contenido completo de un intercambio muy largo que se haya suspendido. Podrá ver la parte inicial del mensaje, pero BizTalk Server está limitado en la cantidad de datos de un intercambio suspendido que puede mostrar.  
  
## <a name="korean-characters-added-to-an-enumeration-in-a-kedifact-schema-must-be-in-unicode"></a>Los caracteres coreanos agregados a una enumeración en un esquema KEDIFACT deben estar en formato UNICODE.  
 Cuando BizTalk Server recibe un intercambio con codificación KEDIFACT con caracteres coreanos, usará el valor de la página de código o del grupo de caracteres que figure en el campo UNB2 para procesar el intercambio. Sin embargo, si modifica un esquema KEDIFACT agregando un carácter coreano con un tipo de datos de Id. a una enumeración, debe agregar el valor en UTF-16 UNICODE, como se especifica en la parte superior del esquema.  
  
## <a name="executing-an-edi-receive-pipeline-from-within-an-orchestration-is-not-supported"></a>No se admite la ejecución de una canalización de recepción EDI desde dentro de una orquestación.  
 En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede ejecutar normalmente las canalizaciones de recepción dentro de una forma de expresión en una orquestación. Esta funcionalidad no se ha probado para las canalizaciones EDIReceive o AS2EdiReceive, por lo que no se admite.  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>La aplicación EDI de BizTalk no debe modificarse.  
 Los artefactos en la aplicación EDI de BizTalk no deben modificarse o eliminarse. Si se modifica esta aplicación, no será posible volver a la aplicación original quitando la configuración o volviendo a configurar las características EDI y AS2.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos del procesamiento de EDI](../core/known-issues-with-edi-processing.md)   
 [Cómo BizTalk Server recibe mensajes EDI](../core/how-biztalk-server-receives-edi-messages.md)   
 [Tutorial (X12): Recibir intercambios EDI y devolución de una confirmación](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)