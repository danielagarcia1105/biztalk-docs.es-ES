---
title: Crear o editar un acuerdo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- agreements, about agreements
- agreements, modifying
- agreements, creating
- agreements
- trading partners, agreements
- creating, agreements
- modifying, agreements
- agreements, trading partners
ms.assetid: 4bbe4b57-d6ec-4448-9c80-2aecd98e0dc7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c49ca06bb8177f76344cdb8ff14c612a7aa52a71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-or-editing-an-agreement"></a>Crear o editar un acuerdo
En este tema se describe cómo crear o editar un acuerdo entre socios comerciales. Un acuerdo entre socios comerciales configura la relación entre dos socios comerciales, incluidos sus identidades; el proceso de la interfaz de socio (PIP); la acción de señal y sincronizar las direcciones URL; y los protocolos asociados.  
  
 Un acuerdo entre socios comerciales incluye la configuración de una configuración del proceso, organización principal, asociado y contrato. Todas estas configuraciones son necesarias para un acuerdo. Puede crear una configuración de proceso basada en un PIP de RosettaNet o un esquema personalizado, pero debe crear la configuración. También debe definir la organización principal y una organización asociada. [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]no se admite el intercambio de mensajes entre entidades desconocidas.  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]procesa y valida un mensaje basado en todas estas configuraciones. Por ejemplo, para un mensaje CIDX, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] valida según la versión de RosettaNet Implementation Framework (RNIF) (solo 1.1), el acuerdo de 0A1 (sin 0A1 solo), y `Is Single Action` propiedad (acción única solo). Un mensaje CIDX validará sólo si se establece la versión RNIF a la versión "1.1", el acuerdo 0A1 a "No 0A1" y el `Is Single Action` propiedad `True`. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]También comprueba que las propiedades del acuerdo son coherentes con la configuración de perfil de configuración de proceso. Por ejemplo, comprobará que ha establecido la `Standard` propiedad del perfil para que "CIDX" y que la propiedad de acuerdo 0A1 del acuerdo se establece en "No 0A1".  
  
 Si cambia un acuerdo mientras un proceso esté activo, puede que observe resultados imprevisibles. Los cambios en las propiedades del acuerdo se aplicarán en cuanto haga clic en **aplicar** o **Aceptar** Aceptar, pero no puede predecir qué fase de un proceso se está ejecutando. Después de cambiar el acuerdo, cualquier actividad nueva en un proceso actual o cualquier proceso nuevo utilizará las propiedades del acuerdo modificada. Sin embargo, un proceso que se ejecuta cuando se cambia el contrato puede ya ha utilizado las propiedades del acuerdo anterior de un mensaje que se está procesando.  
  
 Después de crear un acuerdo, primero debe activarlo para habilitar los mensajes asociados con el acuerdo para enviar o recibir. También puede desactivar un acuerdo para evitar que todos los mensajes asociados con el acuerdo de envío o recepción. Debe desactivar un acuerdo para modificarlo y, a continuación, reactivarla después de editar.  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]guarda esta información en la tabla TPAConfig en la base de datos BTARNCONFIG.  
  
 La configuración en el acuerdo de socio comercial es como se muestra en la siguiente tabla, organizada por pestaña. Los valores predeterminados son los valores utilizados normalmente. Los procedimientos para crear y editar estos valores aparecen después de la tabla.  
  
|Pestaña|Configuración|Uso|  
|---------|-------------|-----------|  
|**General**|**Nombre**|Un nombre único para el contrato, por ejemplo, Fabrikam_To_Contoso_3A2.<br /><br /> Campo obligatorio.|  
|**General**|**Configuración del proceso**|El identificador para el PIP.<br /><br /> Este número identifica qué configuración del proceso está asociado a este contrato.<br /><br /> El valor predeterminado es el primer elemento de la lista de las configuraciones de proceso. La lista desplegable incluye todas las configuraciones de proceso especificado anteriormente.<br /><br /> Campo obligatorio.|  
|**General**|**Mi organización**|La organización principal, seleccionada de una lista desplegable.<br /><br /> Campo obligatorio.|  
|**General**|**Organización de socios comerciales**|La organización del asociado, seleccionada en una lista desplegable.<br /><br /> Campo obligatorio.|  
|**General**|**Description**|Descripción del acuerdo de socio comercial.|  
|**General**|**Versión RNIF**|La versión de la RNIF que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] va a usar para las comunicaciones de acuerdo.<br /><br /> Puede ser **V01.10.00** o **V02.00.01** (valor predeterminado).<br /><br /> Debe ser **V01.10.00** para CIDX.|  
|**General**|**Rol principal**|El rol de la organización principal.<br /><br /> Puede ser la función del iniciador o el rol de servicio de respuesta.|  
|**General**|**Acuerdo de 0A1**|Si [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] devolverá un mensaje de notificación de error (PIP 0A1) cuando se produce un error.<br /><br /> Puede ser **No 0A1** (valor predeterminado) o **0A1**.<br /><br /> Debe ser **No 0A1** para CIDX.|  
|**General**|**Uso**|Indica el tipo de escenario que usará el acuerdo.<br /><br /> Puede ser **prueba** (valor predeterminado) o **producción**.|  
|**General**<br /><br /> (**Adaptador de la aplicación** área)|**Nombre del ensamblado**|El nombre de archivo de la ApplicationAdapter que se puede seleccionar desde el sistema de archivos.<br /><br /> El valor predeterminado es una cadena vacía.|  
|**General**<br /><br /> (**Área de adaptador de la aplicación**)|**Nombre de clase**|El nombre de la clase que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] usará desde el ApplicationAdapter.<br /><br /> El valor predeterminado es \<ninguno >.|  
|**General**<br /><br /> (**Área de adaptador de validación**)|**Nombre del ensamblado**|El nombre de archivo de la ValidationAdapter que se puede seleccionar desde el sistema de archivos. El valor predeterminado es una cadena vacía.|  
|**General**<br /><br /> (**Área de adaptador de validación**)|**Nombre de clase**|El nombre de la clase que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] usará desde el ValidationAdapter.<br /><br /> El valor predeterminado es \<ninguno >.|  
|**Puertos**|**Dirección URL de acción**|La dirección URL a la que la organización principal transmitirá un mensaje de acción. Por ejemplo, http://FabrikamServer/BTARNApp/RNIFReceive.aspx.<br /><br /> Este es un campo obligatorio si se cumplen las siguientes condiciones:<br /><br /> -El **es sincrónico** valor de la configuración del proceso es `False`.<br /><br /> -El **es la única acción** valor de la configuración del proceso es `True`.<br /><br /> -El **rol principal** configuración del acuerdo es **iniciador**.<br /><br /> Esto también es un campo obligatorio si se cumple la siguiente (en cuyo caso, el **dirección URL de la señal** campo también es obligatorio):<br /><br /> -El **es sincrónico** valor de la configuración del proceso es `False`.<br /><br /> -El **es la única acción** valor de la configuración del proceso es `False`.<br /><br /> -Se debe especificar un URI válido en este campo, que comienza por "http://domain" o "https://domain".|  
|**Puertos**|**Dirección URL de señal**|La dirección URL a la que la organización principal transmitirá un mensaje de señal. Por ejemplo, http://FabrikamServer/BTARNApp/RNIFReceive.aspx.<br /><br /> Este es un campo obligatorio si se cumplen las siguientes:<br /><br /> -El **es sincrónico** valor de la configuración del proceso es `False`.<br /><br /> -El **es la única acción** valor de la configuración del proceso es `True`.<br /><br /> -El **rol principal** configuración del acuerdo es **Respondedor**.<br /><br /> Esto también es un campo obligatorio si se cumple la siguiente (en cuyo caso, el **dirección URL de acción** campo también es obligatorio):<br /><br /> -El **es sincrónico** valor de la configuración del proceso es `False`.<br /><br /> -El **es la única acción** valor de la configuración del proceso es `False`.<br /><br /> Debe especificar un URI válido en este campo, que comienza por "http://domain" o "https://domain".|  
|**Puertos**|**Dirección URL de la sincronización**|La dirección URL que usará la organización principal para establecer una conexión a través del adaptador HTTP. Por ejemplo, http://FabrikamServer/BTARNApp/RNIFReceive.aspx.<br /><br /> Este es un campo obligatorio si se cumplen las siguientes:<br /><br /> -El **es sincrónico** valor de la configuración del proceso es `True`.<br /><br /> -El **rol principal** configuración del acuerdo es **iniciador**.<br /><br /> Debe especificar un URI válido en este campo, que comienza por "http://domain" o "https://domain".|  
|**Protocolo**|**Método implícita**|El protocolo utilizado para calcular el resumen de los mensajes entrantes para fines sin repudio.<br /><br /> **A partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] y versiones más recientes**, soporte técnico SHA2 se incluye automáticamente. Las opciones incluyen: **MD5**, **SHA-1**, **SHA-256** (valor predeterminado), **SHA-384**, y **SHA-512**.<br /><br />Para anterior [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] versiones, las opciones incluyen **MD5** o **SHA-1** (valor predeterminado).<br /><br /> El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibir canalización recibe y descifra un mensaje, incluso si el protocolo utilizado para cifrar el mensaje y la **codificación** no coinciden con la configuración de esta ficha del acuerdo. Por lo tanto, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibe mensajes cifrados en RC2-40 o 3DES.<br /><br /> Todos los mensajes firmados salientes tienen una síntesis de SHA-1.|  
|**Protocolo**|**Codificar todos los elementos**|Si el sistema codificará juntas todas las partes de mensaje de varias partes.<br /><br /> Puede ser `True` o `False` (valor predeterminado).<br /><br /> Cuando`True`, todas las partes de mensaje de varias partes se codificarán juntos mediante el método indicado por el `Encoding` propiedad.<br /><br /> Cuando `False`, el sistema sólo codificará los archivos adjuntos mediante el método indicado por el `Encoding` propiedad. (Los datos adjuntos siempre se codifican mediante la canalización de envío mediante el método indicado por el `Encoding` propiedad.) De forma predeterminada, al establecer esta propiedad en `False`, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] codifica las otras partes del mensaje (de cuatro partes en RNIF 2.01, tres partes en RNIF 1.1) en formato Entrecomillado imprimible.|  
|**Protocolo**|**Codificación**|El protocolo utilizado para codificar todos los elementos (si la **codificar todas las partes** cuadro es `True`) o los datos adjuntos (si la **codificar todas las partes** cuadro es `False`).<br /><br /> Puede ser **8bits**, **base 64** (valor predeterminado), o **Entrecomillado imprimible**.|  
|**Protocolo**|**Algoritmo de cifrado**|El algoritmo utilizado para cifrar los mensajes entrantes y salientes.<br /><br /> **A partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] y versiones más recientes**, compatibilidad con AES se incluye automáticamente. Las opciones incluyen **RC2-40**, **3DES**, **AES128** (valor predeterminado), **AES192**, y **AES256**. <br /><br />Para anterior [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] versiones, las opciones incluyen **RC2-40** (valor predeterminado) o **3DES**.<br /><br /> El algoritmo de cifrado solo surte efecto si se ha establecido la `Is Persistent Confidentiality Required` propiedad como **carga** o **contenedor de carga** en la configuración del proceso correspondiente.|  
|**Protocolo**|**Dirección de cifrado**|Si el sistema cifrará el mensaje entrante, el mensaje saliente o ambos.<br /><br /> Puede ser **entrada**, **saliente**, o **entrante o saliente** (valor predeterminado).<br /><br /> La configuración de dirección de cifrado solo surte efecto si se ha establecido la `Is Persistent Confidentiality Required` propiedad como **carga** o **contenedor de carga** en la configuración del proceso correspondiente.|  
|**Propiedades personalizadas**|**Nombre**|Nombre de la propiedad personalizada.<br /><br /> Puede establecer propiedades personalizadas en una base por contrato. Si crea un nuevo proceso privado personalizado, puede usar estas propiedades personalizadas en el procesamiento de diferentes contratos.<br /><br /> Puede usar el `RuntimeConfig.GetTPACustomConfigValue` método en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK para recuperar las propiedades personalizadas de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuración.<br /><br /> El `Name` propiedad debe ser únicos y no está vacío.<br /><br /> Puede escribir los siguientes valores personalizados:<br /><br /> - **AAR**. Se trata de la propiedad personalizada requiere confirmación de aceptación. Esto sólo se aplica a RNIF 1.1. Establezca esta propiedad en **false** (que no distingue entre mayúsculas y minúsculas) para requerir sólo una confirmación de recepción, no una confirmación de aceptación. Si **AAR** está establecido en algo distinto de **false**, a continuación, el proceso público Respondedor debe enviar una confirmación de aceptación y el proceso público de iniciador esperará una confirmación de aceptación. Si AAR se establece en false, los procesos públicos se completará después de la confirmación de recepción.<br /><br /> - **HPCC**. Éste es el código de clasificación de inicio asociado. Esto sólo se aplica a RNIF 1.1. Esto le permite establecer el elemento GlobalPartnerClassificationCode para el socio principal en el encabezado de servicio de un mensaje saliente a la entrada en la columna valor. Este valor invalida la propiedad de clasificación de la organización de inicio en la configuración de la organización principal. Utilice esta propiedad personalizada cuando la organización principal puede tener más de una clasificación.<br /><br /> - **PPCC**. Éste es el código de clasificación de perfil de socio comercial. Esto sólo se aplica a RNIF 1.1. Esto le permite establecer el elemento GlobalPartnerClassificationCode para el socio comercial en el encabezado de servicio de un mensaje saliente a la entrada en la columna valor. Este valor invalida la propiedad de clasificación de socio comercial en la configuración del socio comercial. Utilice esta propiedad personalizada cuando el socio puede tener más de una clasificación.|  
|**Propiedades personalizadas**|**Valor**|Valor de la propiedad personalizada.|  
  
### <a name="to-create-a-trading-partner-agreement"></a>Para crear un acuerdo de socio comercial  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
2.  En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  
  
3.  Haga clic en **contratos**, seleccione **New**y, a continuación, haga clic en **acuerdo**.  
  
4.  En el cuadro de diálogo Propiedades del acuerdo nuevo, en la **General**, **puertos**, **protocolo**, y **propiedades personalizadas** pestañas, escriba los valores para la configuración. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  
  
5.  Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  BTARN no aceptará mensajes relacionados con el acuerdo hasta que Active el acuerdo.  
  
6.  Haga clic en el nombre del acuerdo en el panel derecho y, a continuación, haga clic en **activar**.  
  
> [!NOTE]
>  Si ya ha activado un acuerdo, haga clic en el nombre del acuerdo en el panel derecho y, a continuación, haga clic en **desactivar** para impedir que todos los mensajes asociados con el acuerdo de envío o recepción.  
  
### <a name="to-edit-a-trading-partner-agreement"></a>Para editar un acuerdo entre socios comerciales  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
2.  En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en el **contratos** nodo.  
  
3.  Haga clic en el acuerdo que desea editar y, a continuación, haga clic en **propiedades**.  
  
4.  En el  **\<**  *nombre del contrato*  **>**  cuadro de diálogo de propiedades de la **General** y  **Póngase en contacto con propiedades** pestañas, cambiar la configuración según sea necesario. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)   
 [Administrar la configuración de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)