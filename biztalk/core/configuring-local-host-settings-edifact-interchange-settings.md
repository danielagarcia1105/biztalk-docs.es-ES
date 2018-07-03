---
title: Configuración del Host Local (configuración de intercambio EDIFACT) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1cf8696-d1f4-49aa-aa0a-ecf66f55e01d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 894463d274afb886f2595492afc9372bf111cb29
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965829"
---
# <a name="configuring-local-host-settings-edifact-interchange-settings"></a>Configuración de las opciones de host local (configuración de intercambio EDIFACT)
La configuración de host local rige cómo se procesan los intercambios EDI. La configuración de esta página puede dividirse en dos categorías: configuración del receptor (para intercambios de entrada) y configuración del remitente (para intercambios de salida). Como parte de la configuración del receptor, puede especificar si un lote entrante se dividirá en conjuntos de transacciones o se conservará tal cual. Si se conserva, puede especificar si BizTalk Server suspende el intercambio o el conjunto de transacciones en caso de que se produzca un error. Como parte de la configuración del remitente, se puede especificar cómo se generan los números de control de mensajes de salida.  
  
> [!IMPORTANT]
>  Las siguientes propiedades están deshabilitadas en **entidad A -> entidad B** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad**casilla de verificación de la entidad A.  
> 
> - Todas las propiedades de la **configuración del remitente** sección.  
> 
>   De forma similar, las propiedades siguientes están deshabilitadas en la misma página en el **parte B -> entidad A** pestaña si ha seleccionado la casilla de verificación al crear la entidad A.  
> 
> - Todas las propiedades de la **configuración del receptor** sección.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-local-host--receivers-settings"></a>Para configurar el host local – configuración del receptor  
  
1. Cree un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2. En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **configuración de Host Local**.  
  
3. En el **EDIFACT ACK** sección, para designar los números de referencia de conjunto de transacciones que se usará en una confirmación, escriba un valor para el prefijo, un intervalo de números de referencia y el sufijo.  
  
    Haga clic en **restablecer** Restablecer actual conjunto de transacciones en el límite inferior. Seleccione **restablecer al límite inferior cuando se encuentra fuera del límite** tener [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] restablecer el número de referencia en el límite inferior del valor de intervalo si se supera el límite máximo.  
  
4. Desactive el **enrutar confirmación para la canalización de envío de solicitud-respuesta de puerto de recepción** para devolver la confirmación a través de otro puerto de envío. Deje la propiedad seleccionada para devolver la confirmación en el puerto de envío asociado con el puerto de recepción de solicitud-respuesta bidireccional.  
  
5. Borrar **enmascarar información de autorización y seguridad de contraseña** deshabilitar el enmascaramiento de información de seguridad de autorización/contraseña (los campos UNB6.1 y UNB6.2) en la propiedad de contexto para evitar la divulgación de información.  
  
   > [!NOTE]
   >  Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe mensajes, promociona el encabezado UNB en el contexto del mensaje. Si no se enmascara, la información de seguridad dentro del contexto estará disponible para cualquier usuario con privilegios administrativos. Para enmascarar esta información, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reemplaza cada carácter de la información con un **#** caracteres. Este es un proceso unidireccional: el **#** caracteres no se puede convertir en caracteres reales.  
  
6. En el **opción de procesamiento por lotes de entrada** lista desplegable, haga lo siguiente:  
  
   1.  Seleccione la opción predeterminada **dividir intercambio como conjuntos de transacciones: suspender conjuntos de transacciones en Error** para especificar que BizTalk Server debe analizar cada conjunto de transacciones en un intercambio en un documento XML independiente. Después, BizTalk Server aplicará el sobre adecuado al conjunto de transacciones y enrutará el documento de este conjunto al cuadro de mensajes. Con esta opción, si uno o varios conjuntos de transacciones del intercambio no superan la validación, BizTalk Server suspenderá solo esos conjuntos de transacciones.  
  
   2.  Seleccione **dividir intercambio como conjuntos de transacciones: suspender intercambio en el Error** para especificar que BizTalk Server debe analizar cada conjunto de transacciones en un intercambio en un documento XML independiente. Después, BizTalk Server aplicará el sobre adecuado al conjunto de transacciones y enrutará el documento de este conjunto al cuadro de mensajes. Con esta opción, si uno o varios conjuntos de transacciones en el intercambio no superan la validación, BizTalk Server suspenderá el intercambio completo.  
  
   3.  Seleccione **conservar intercambio: suspender intercambio en caso de un Error** para especificar que BizTalk Server debe dejar el intercambio intacto y crear un documento XML para todo el intercambio por lotes. Con esta opción, si uno o varios conjuntos de transacciones en el intercambio no superan la validación, BizTalk Server suspenderá el intercambio completo.  
  
   4.  Seleccione **conservar intercambio: suspender conjuntos de transacciones en Error** para especificar que BizTalk Server debe dejar el intercambio intacto y crear un documento XML para todo el intercambio por lotes. Con esta opción, si uno o varios conjuntos de transacciones del intercambio no superan la validación, BizTalk Server suspenderá solo esos conjuntos de transacciones, sin dejar de procesar todos los demás conjuntos de transacciones.  
  
       > [!NOTE]
       >  Si selecciona **conservar intercambio: suspender intercambio en caso de un Error** o **conservar intercambio: suspender conjuntos de transacciones en Error**, los valores de propiedad en el **definición de segmento ISA**  y **GS y ST definición de segmento** páginas (que determinan cómo BizTalk Server creará los encabezados ISA, GS y ST de un intercambio saliente) no se aplican. Los encabezados de intercambios, grupos y conjuntos de transacciones que existen en el intercambio que se conserva quedan retenidos cuando la canalización de envío lo procesa para su envío.  
  
### <a name="to-configure-local-host--senders-settings"></a>Procedimiento para configurar el host local – configuración del remitente  
  
1.  Para **número de control de intercambio (UNB5)**, especifique un intervalo de valores para el número de control de intercambio que se usará el servidor BizTalk Server en generar un intercambio saliente. Especifique un valor numérico con un mínimo de 1 y un máximo de 999999999. Se trata de un campo obligatorio.  
  
    > [!NOTE]
    >  El primer campo (**UNB5.1**) es el prefijo; el segundo y el tercer campo (**UNB5.2**) contienen el intervalo de números que se usará como el número de control de intercambio; y el cuarto campo (**UNB5.3**) es el sufijo. El prefijo y el sufijo son opcionales; el número de control es obligatorio. El número de control aumenta para cada mensaje nuevo; el prefijo y el sufijo continúan siendo el mismo. El número máximo de caracteres es 14 para el número de control, 13 para el prefijo y el sufijo, y 14 para los tres campos combinados.  
    >   
    >  Para restablecer el número de control en el valor mínimo especificado, haga clic en el **restablecer** botón. Comprobar **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer automáticamente al valor mínimo si se supera el valor máximo.  
  
2.  Para **número de control de grupo (UNG5)**, escriba el prefijo, que hacen referencia a intervalo de números y el sufijo que BizTalk Server debe usar para el número de control de grupo del primer intercambio que envía.  
  
    > [!NOTE]
    >  El primer campo (**UNG5.1**) es el prefijo; el segundo y el tercer campo (**UNG5.2**) contienen el intervalo de números que se utilizará para el número de control de grupo; y el cuarto campo (**UNG5.3**) es el sufijo. El prefijo y el sufijo son opcionales; el número de control es obligatorio. El número de control aumenta para cada mensaje nuevo, hasta que se alcanza el valor máximo; el prefijo y el sufijo continúan siendo el mismo. Sólo se permiten números en **UNG5.2**. El número máximo de caracteres es 14 para el número de control, 13 para el prefijo y el sufijo, y 14 para los tres campos combinados.  
    >   
    >  Para restablecer el número de control de grupo en el valor mínimo especificado, haga clic en el **restablecer** botón. Comprobar **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer automáticamente al valor mínimo si se supera el valor máximo.  
  
3.  Para **encabezado del mensaje (UNH)**, haga clic en **aplicar Id. nuevo**, escriba el prefijo, escriba el intervalo de números de referencia y escriba el sufijo que BizTalk Server debe usar para el número de referencia de conjunto de transacciones.  
  
    > [!NOTE]
    >  El primer campo (**UNH1.1**) es el prefijo; el segundo y el tercer campo (**UNH1.2**) son el intervalo de números de referencia; y el cuarto campo (**UNH1.3**) es el sufijo. El prefijo y el sufijo son opcionales; el número de referencia es obligatorio. El número de referencia aumenta para cada mensaje nuevo; el prefijo y el sufijo continúan siendo el mismo. El intervalo de valores predeterminado para el número referencia es de 1 a 99999999999999. Sólo se permiten números en **UNH1.2**. El número máximo de caracteres es 14 para el número de control, 13 para el prefijo y el sufijo, y 14 para los tres campos combinados.  
    >   
    >  Para restablecer actual del conjunto de transacciones número de control en el valor mínimo, haga clic en **restablecer**. Seleccione **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer el número de control al valor mínimo si se ha superado el valor máximo.  
  
4.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las opciones de intercambio (EDIFACT)](../core/configuring-interchange-settings-edifact.md)