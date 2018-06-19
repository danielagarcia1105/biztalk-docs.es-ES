---
title: Configuración del Host Local (configuración de intercambio de X12) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c66c1e63-c654-4ccb-b424-34c06f1ce94e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10172c700d8b3d8d2039e46f28d24ff39ba93aac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234756"
---
# <a name="configuring-local-host-settings-x12-interchange-settings"></a>Configuración de las opciones de host local (configuración de intercambio X12)
La configuración de host local rige cómo se procesan los intercambios EDI. La configuración de esta página puede dividirse en dos categorías: configuración del receptor (para intercambios de entrada) y configuración del remitente (para intercambios de salida). Como parte de la configuración del receptor, puede especificar si un lote entrante se dividirá en conjuntos de transacciones o se conservará tal cual. Si se conserva, puede especificar si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspende el intercambio o el conjunto de transacciones en caso de que se produzca un error. Como parte de la configuración del remitente, se puede especificar cómo se generan los números de control de los mensajes de salida.  
  
> [!NOTE]
>  La configuración descrita aquí también se aplica a los intercambios HIPAA.  
  
> [!IMPORTANT]
>  Las propiedades siguientes están deshabilitadas en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado el **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad**casilla de verificación de la entidad A.  
>   
>  -   Todas las propiedades de la **configuración del remitente** sección.  
>   
>  De forma similar, las propiedades siguientes están deshabilitadas en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.  
>   
>  -   Todas las propiedades de la **configuración del receptor** sección.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-local-host--receivers-settings"></a>Para configurar el host local – configuración del receptor  
  
1.  Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **configuración de Host Local**.  
  
3.  Desactive el **puerto de recepción de enrutar confirmación para la canalización de envío de solicitud-respuesta** para devolver la confirmación por otro puerto de envío. Deje la propiedad seleccionada para devolver la confirmación en el puerto de envío asociado con el puerto de recepción de solicitud-respuesta bidireccional.  
  
4.  Para designar el intervalo de números de control de conjunto de transacciones utilizados en una confirmación, escriba valores en la **número de Control de confirmación (ST02)** campos. Especifique un valor numérico para los dos campos que quedan en la mitad y un valor alfanumérico (si desea) para los campos de prefijo y sufijo. Los campos que quedan en la mitad son necesarios y contienen los valores mínimo y máximo para el número de control, el prefijo y el sufijo son opcionales. La longitud máxima de los tres campos es de nueve caracteres.  
  
     Restablecer actual del conjunto de transacciones número de control en el valor mínimo, haga clic en **restablecer**. Comprobar **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer el número de control en el límite inferior una vez que ha superado el valor máximo.  
  
5.  Seleccione **enmascarar información de autorización y seguridad de contraseña en la propiedad de contexto** casilla de verificación para habilitar la máscara de información de seguridad de autorización/contraseña (los campos ISA2 e ISA4) en la propiedad de contexto para evitar que la información divulgación de información.  
  
    > [!NOTE]
    >  Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe mensajes, promociona el encabezado ISA en el contexto del mensaje. Si no se enmascara, la información de seguridad dentro del contexto estará disponible para cualquier usuario con privilegios administrativos. Para enmascarar esta información, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reemplaza cada carácter de la información con un  **#**  caracteres. Se trata de un proceso unidireccional: el  **#**  caracteres no se puede convertir en caracteres reales.  
  
6.  En el **opción de procesamiento por lotes de entrada** lista desplegable, haga lo siguiente:  
  
    1.  Seleccione la opción predeterminada **dividir intercambio como conjuntos de transacciones: suspender conjuntos de transacciones en caso de Error** para especificar que BizTalk Server debe analizar cada conjunto de transacciones en un intercambio en un documento XML independiente. Después, BizTalk Server aplicará el sobre adecuado al conjunto de transacciones y enrutará el documento de este conjunto al cuadro de mensajes. Con esta opción, si uno o varios conjuntos de transacciones del intercambio no superan la validación, BizTalk Server suspenderá solo esos conjuntos de transacciones.  
  
    2.  Seleccione **dividir intercambio como conjuntos de transacciones: suspender intercambio en caso de Error** para especificar que BizTalk Server debe analizar cada conjunto de transacciones en un intercambio en un documento XML independiente. Después, BizTalk Server aplicará el sobre adecuado al conjunto de transacciones y enrutará el documento de este conjunto al cuadro de mensajes. Con esta opción, si uno o varios conjuntos de transacciones en el intercambio no superan la validación, BizTalk Server suspenderá el intercambio completo.  
  
    3.  Seleccione **conservar intercambio: suspender intercambio en caso de Error** para especificar que BizTalk Server debe dejar el intercambio intacto y crear un documento XML para todo el intercambio por lotes. Con esta opción, si uno o varios conjuntos de transacciones en el intercambio no superan la validación, BizTalk Server suspenderá el intercambio completo.  
  
    4.  Seleccione **conservar intercambio: suspender conjuntos de transacciones en caso de Error** para especificar que BizTalk Server debe dejar el intercambio intacto y crear un documento XML para todo el intercambio por lotes. Con esta opción, si uno o varios conjuntos de transacciones en el intercambio no superan la validación, BizTalk Server suspenderá solo esos conjuntos de transacciones, pero continuará con el procesamiento de todos los demás conjuntos de transacciones.  
  
        > [!NOTE]
        >  Si selecciona **conservar intercambio: suspender intercambio en caso de Error** o **conservar intercambio: suspender conjuntos de transacciones en caso de Error**, el intercambio, grupo y transacción establecen las propiedades de segmento (que determinar cómo BizTalk Server creará los encabezados ISA, GS y ST de un intercambio saliente) no se aplican. Los encabezados de intercambios, grupos y conjuntos de transacciones que existen en el intercambio que se conserva quedan retenidos cuando la canalización de envío lo procesa para su envío.  
  
### <a name="to-configure-local-host--senders-settings"></a>Procedimiento para configurar el host local – configuración del remitente  
  
1.  Para **número de control de intercambio (ISA13)**, especifique un intervalo de valores para el número de control de intercambio que se usará el servidor BizTalk Server para generar un intercambio saliente. Especifique un valor numérico con un mínimo de 1 y un máximo de 999999999. Se trata de un campo obligatorio.  
  
     Para restablecer el número de control en el valor mínimo especificado, haga clic en el **restablecer** botón. Comprobar **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer automáticamente al valor mínimo si se supera el valor máximo.  
  
2.  Para **número de control de grupo (GS06)**, escriba el intervalo de números que BizTalk Server debe usar para el número de control de grupo. Especifique un valor numérico con un mínimo de un carácter y un máximo de nueve caracteres. Este campo es obligatorio.  
  
     Para restablecer el número de control de grupo para el valor mínimo especificado, haga clic en el **restablecer** botón. Comprobar **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer automáticamente al valor mínimo si se supera el valor máximo.  
  
3.  Para **número de Control de conjunto de transacciones (ST02)**, haga clic en **aplicar Id. nuevo** y, a continuación, escriba un intervalo de valores numéricos para los campos obligatorios centrales y valores alfanuméricos para el prefijo y sufijo opcionales. La longitud máxima de los cuatro campos es de nueve caracteres.  
  
     Restablecer actual del conjunto de transacciones número de control en el valor mínimo, haga clic en **restablecer**. Seleccione **restablecer al límite inferior cuando se encuentra fuera del límite** para restablecer el número de control en el valor mínimo si se ha superado el valor máximo.  
  
4.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de intercambio (X12)](../core/configuring-interchange-settings-x12.md)