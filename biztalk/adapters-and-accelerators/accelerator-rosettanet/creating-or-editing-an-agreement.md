---
title: Crear o editar un acuerdo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bbe4b57-d6ec-4448-9c80-2aecd98e0dc7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 404182fda241afa6876142925ec449f1bae3c6ce
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753036"
---
# <a name="creating-or-editing-an-agreement"></a>Crear o editar un acuerdo
Este tema describe cómo crear o editar un acuerdo entre socios comerciales. Un acuerdo entre socios comerciales configura la relación entre dos socios comerciales, incluidos sus identidades; el proceso de interfaz de socio (PIP); la acción, de señal y sincronización de direcciones URL; y los protocolos asociados.  

 Un acuerdo entre socios comerciales incluye la configuración de una configuración del proceso, organización principal, socios y contrato. Todas estas configuraciones son necesarias para un acuerdo. Puede crear una configuración de proceso basada en un PIP de RosettaNet o un esquema personalizado, pero debe crear la configuración. También debe definir la organización principal y una organización asociada. Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] no admite el intercambio de mensajes entre entidades desconocidas.  

 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] procesa y valida un mensaje basado en todas estas configuraciones. Por ejemplo, para un mensaje CIDX [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] valida según la versión de RosettaNet Implementation Framework (RNIF) (solo 1.1), de acuerdo 0A1 (sin 0A1 solo), y `Is Single Action` propiedad (acción única solo). Un mensaje CIDX validará solo si establece la versión RNIF "1.1", el acuerdo 0A1 a "No 0A1" y el `Is Single Action` propiedad `True`. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] también valida que las propiedades del acuerdo son coherentes con el perfil de configuración de proceso. Por ejemplo, comprobará que ha establecido la `Standard` propiedad del perfil de "CIDX" y que la propiedad de acuerdo 0A1 del acuerdo se establece en "Ninguna 0A1".  

 Si cambia un acuerdo mientras un proceso está activo, que observe resultados imprevisibles. Los cambios en las propiedades del acuerdo se aplicarán, en cuanto haga clic en **aplicar** o **Aceptar** Aceptar, pero no puede predecir qué fase de un proceso se está ejecutando. Después de cambiar el contrato, cualquier actividad en un proceso actual o cualquier nuevo proceso usará las propiedades del acuerdo modificada. Sin embargo, un proceso en ejecución cuando cambie el contrato es posible que ya ha utilizado las propiedades del acuerdo anterior para un mensaje que se está procesando.  

 Después de crear un acuerdo, debe activarlo para permitir que los mensajes asociados con el acuerdo para enviar o recibir. También puede desactivar un acuerdo para evitar que los mensajes asociados con el acuerdo de envío o recepción. Debe desactivar un acuerdo para modificarlo y, a continuación, volver a activarla después de editar.  

 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Esta información se guarda en la tabla TPAConfig en la base de datos BTARNCONFIG.  

 La configuración en el acuerdo entre socios comerciales es como se muestra en la siguiente tabla, organizada por pestaña. Los valores predeterminados son los valores que normalmente se usan más. Los procedimientos para crear y editar estos valores aparecen después de la tabla.  


|                          Pestaña                           |          Parámetro          |  Uso  |
|---|---|---|
|                      **General**                       |         **Nombre**          |  Un nombre único para el contrato, por ejemplo, Fabrikam_To_Contoso_3A2.<br /><br /> Campo obligatorio. |
|                      **General**                       | **Configuración del proceso** | El identificador para el PIP.<br /><br /> Este número identifica qué configuración del proceso está asociado con este acuerdo.<br /><br /> El valor predeterminado es el primero en la lista de las configuraciones de proceso. La lista desplegable incluye todas las configuraciones de proceso especificado anteriormente.<br /><br /> Campo obligatorio. |
|                      **General**                       |    **Mi organización**    |  La organización principal, seleccionada de una lista desplegable.<br /><br /> Campo obligatorio. |
|                      **General**                       | **Organización del asociado**  | La organización del asociado, seleccionada de una lista desplegable.<br /><br /> Campo obligatorio. |
|                      **General**                       |      **Descripción**      |  Descripción del acuerdo de socio comercial.|
|                      **General**                       |     **Versión RNIF**      | La versión de la RNIF que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] usarán para las comunicaciones de acuerdo.<br /><br /> Puede ser **V01.10.00** o **V02.00.01** (predeterminado).<br /><br /> Debe ser **V01.10.00** para CIDX. |
|                      **General**                       |       **Rol principal**       | El rol de la organización principal.<br /><br /> Puede ser un rol del iniciador o el rol de servicio de respuesta. |
|                      **General**                       |     **Contrato 0A1**     | Si [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] devolverá un mensaje de notificación de error (PIP 0A1) cuando se produce un error.<br /><br /> Puede ser **ningún 0A1** (valor predeterminado) o **0A1**.<br /><br /> Debe ser **ningún 0A1** para CIDX. |
|                      **General**                       |         **Usage**         | Indica el tipo de escenario que usará el acuerdo.<br /><br /> Puede ser **prueba** (valor predeterminado) o **producción**. |
| **General**<br /><br /> (**Adaptador de aplicación** área) |     **Nombre del ensamblado**     | El nombre de archivo de la ApplicationAdapter que se puede seleccionar desde el sistema de archivos.<br /><br /> El valor predeterminado es una cadena vacía.  |
| **General**<br /><br /> (**Área de aplicación de adaptador**) |      **Nombre de clase**       | El nombre de la clase que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] usará desde el ApplicationAdapter.<br /><br /> El valor predeterminado es \<ninguno\>. |
| **General**<br /><br /> (**Área de adaptador de validación**)  |     **Nombre del ensamblado**     | El nombre de archivo de la ValidationAdapter que se puede seleccionar desde el sistema de archivos. El valor predeterminado es una cadena vacía.  |
| **General**<br /><br /> (**Área de adaptador de validación**)  |      **Nombre de clase**       | El nombre de la clase que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] usará desde el ValidationAdapter.<br /><br /> El valor predeterminado es \<ninguno\>. |
|                       **Puertos**                        |      **Dirección URL de acción**       | La dirección URL a la que la organización principal transmitirá un mensaje de acción. Por ejemplo, `http://FabrikamServer/BTARNApp/RNIFReceive.aspx`.<br /><br /> Este es un campo obligatorio si se cumplen todas las siguientes:<br /><br /> -El **Is Synchronous** es la opción de configuración de proceso `False`.<br /><br /> -El **es la única acción** es la opción de configuración de proceso `True`.<br /><br /> -El **rol principal** es la configuración del acuerdo **iniciador**.<br /><br /> Esto también es un campo obligatorio si se cumple lo siguiente (en cuyo caso el **URL de la señal** campo también se requiere):<br /><br /> -El **Is Synchronous** es la opción de configuración de proceso `False`.<br /><br /> -El **es la única acción** es la opción de configuración de proceso `False`.<br /><br /> -Se debe especificar un URI válido en este campo, que comienza con una "<`http://domain`>" o "<`https://domain`>".  |
|                       **Puertos**                        |      **URL de la señal**       | La dirección URL a la que la organización principal transmitirá un mensaje de señal. Por ejemplo, `http://FabrikamServer/BTARNApp/RNIFReceive.aspx`.<br /><br /> Este es un campo obligatorio si se cumplen los siguientes:<br /><br /> -El **Is Synchronous** es la opción de configuración de proceso `False`.<br /><br /> -El **es la única acción** es la opción de configuración de proceso `True`.<br /><br /> -El **rol principal** es la configuración del acuerdo **Respondedor**.<br /><br /> Esto también es un campo obligatorio si se cumple lo siguiente (en cuyo caso el **dirección URL de acción** campo también se requiere):<br /><br /> -El **Is Synchronous** es la opción de configuración de proceso `False`.<br /><br /> -El **es la única acción** es la opción de configuración de proceso `False`.<br /><br /> Debe especificar un URI válido en este campo, que comienza con una "<`http://domain`>" o "<`https://domain`>".  |
|                       **Puertos**                        |       **Dirección URL de la sincronización**        | La dirección URL que la organización principal que usará para establecer una conexión a través del adaptador HTTP. Por ejemplo, `http://FabrikamServer/BTARNApp/RNIFReceive.aspx`.<br /><br /> Este es un campo obligatorio si se cumplen los siguientes:<br /><br /> -El **Is Synchronous** es la opción de configuración de proceso `True`.<br /><br /> -El **rol principal** es la configuración del acuerdo **iniciador**.<br /><br /> Debe especificar un URI válido en este campo, que comienza con una "<`http://domain`>" o "<`https://domain`>".  |
|                      **Protocolo**                      |     **Método de síntesis**     | El protocolo utilizado para calcular la síntesis de mensajes entrantes para fines sin repudio.<br /><br /> **A partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] y las versiones más recientes**, soporte técnico de SHA2 se incluye automáticamente. Las opciones incluyen: **MD5**, **SHA-1**, **SHA-256** (valor predeterminado), **SHA-384**, y **SHA-512**.<br /><br />Para anterior [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] versiones, las opciones incluyen **MD5** o **SHA-1** (valor predeterminado).<br /><br /> El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibir canalización recibe y descifra un mensaje, incluso si el protocolo utilizado para cifrar el mensaje y el **Encoding** no coinciden con la configuración de esta ficha del acuerdo. Por lo tanto, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibe mensajes cifrados en RC2 40 o 3DES.<br /><br /> Todos los mensajes salientes con signo tienen un resumen de SHA-1. |
|                      **Protocolo**                      |   **Codificar en todas partes**    | Si el sistema codificará juntas todas las partes del mensaje de varias partes.<br /><br /> Puede ser `True` o `False` (valor predeterminado).<br /><br /> Cuando`True`, todas las partes del mensaje de varias partes se codificarán entre sí mediante el método indicado por el `Encoding` propiedad.<br /><br /> Cuando `False`, el sistema solo se van a codificar los datos adjuntos con el método indicado por el `Encoding` propiedad. (Los datos adjuntos siempre se codifican por la canalización de envío mediante el método indicado por el `Encoding` propiedad.) De forma predeterminada, al establecer esta propiedad en `False`, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] codifica las otras partes del mensaje (cuatro partes en RNIF 2.01, tres partes en RNIF 1.1) en formato Entrecomillado imprimible. |
|                      **Protocolo**                      |       **Codificación**        | El protocolo utilizado para codificar todos los elementos (si la **codificar todas las partes** cuadro es `True`) o los datos adjuntos (si la **codificar todas las partes** cuadro es `False`).<br /><br /> Puede ser **de 8 bits**, **base 64** (valor predeterminado), o **Entrecomillado imprimible**. |
|                      **Protocolo**                      | **Algoritmo de cifrado**  | El algoritmo utilizado para cifrar los mensajes entrantes y salientes.<br /><br /> **A partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] y las versiones más recientes**, compatibilidad con AES se incluye automáticamente. Las opciones incluyen **RC2 40**, **3DES**, **AES128** (valor predeterminado), **AES192**, y **AES256**. <br /><br />Para anterior [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] versiones, las opciones incluyen **RC2 40** (valor predeterminado) o **3DES**.<br /><br /> El algoritmo de cifrado solo surte efecto si se ha establecido la `Is Persistent Confidentiality Required` propiedad como **carga** o **contenedor de carga** en la configuración del proceso correspondiente. |
|                      **Protocolo**                      | **Dirección de cifrado**  |  Si el sistema cifrará el mensaje entrante, el mensaje saliente o ambos.<br /><br /> Puede ser **entrante**, **saliente**, o **entrante o saliente** (predeterminado).<br /><br /> El valor de dirección de cifrado solo surte efecto si se ha establecido la `Is Persistent Confidentiality Required` propiedad como **carga** o **contenedor de carga** en la configuración del proceso correspondiente. |
|                 **Propiedades personalizadas**                  |         **Nombre**          | Nombre de la propiedad personalizada.<br /><br /> Puede establecer las propiedades personalizadas en una base por acuerdo. Si crea un nuevo proceso privado personalizado, puede usar estas propiedades personalizadas en el procesamiento de distintos acuerdos.<br /><br /> Puede usar el `RuntimeConfig.GetTPACustomConfigValue` método en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK para recuperar las propiedades personalizadas del [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuración.<br /><br /> El `Name` propiedad debe ser únicos y no está vacío.<br /><br /> Puede escribir los valores personalizados siguientes:<br /><br /> - **AAR**. Se trata de la propiedad personalizada requiere confirmación de aceptación. Esto solo se aplica para RNIF 1.1. Establezca esta opción en **false** (que no distingue mayúsculas de minúsculas) para solicitar solo una confirmación de recepción, no una confirmación de aceptación. Si **AAR** está establecido en algo distinto **false**, a continuación, el proceso público del Respondedor debe enviar una confirmación de aceptación y el proceso público del iniciador esperará una confirmación de aceptación. Si AAR está establecida en false, los procesos públicos se completará después de la confirmación de recepción.<br /><br /> - **HPCC**. Este es el código de clasificación de inicio asociado. Esto solo se aplica para RNIF 1.1. Esto le permite establecer el elemento GlobalPartnerClassificationCode para el socio principal en el encabezado de servicio de un mensaje saliente a la entrada en la columna valor. Este valor invalida la propiedad de clasificación de organización principal en la configuración de la organización principal. Utilice esta propiedad personalizada cuando la organización principal puede tener más de una clasificación.<br /><br /> - **PPCC**. Este es el código de clasificación de perfil de socio. Esto solo se aplica para RNIF 1.1. Esto le permite establecer el elemento GlobalPartnerClassificationCode para el socio comercial en el encabezado de servicio de un mensaje saliente a la entrada en la columna valor. Este valor invalida la propiedad de clasificación asociado en la configuración del socio comercial. Utilice esta propiedad personalizada cuando el asociado puede tener más de una clasificación. |
|                 **Propiedades personalizadas**                  |         **Valor**         |  Valor de la propiedad personalizada. |

## <a name="create-a-trading-partner-agreement"></a>Crear un acuerdo entre socios comerciales  

1. Haga clic en **Inicio**, elija **Todos los programas**, elija **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Consola de administración**.  

2. En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  

3. Haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **contrato**.  

4. En el cuadro de diálogo Propiedades de nuevo contrato, en el **General**, **puertos**, **protocolo**, y **propiedades personalizadas** pestañas, escriba los valores para la configuración. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  

5. Haga clic en **Aceptar**.  

   > [!NOTE]
   >  BTARN no aceptará mensajes relacionados con el acuerdo hasta que Active el acuerdo.  

6. Haga clic en el nombre del contrato en el panel derecho y, a continuación, haga clic en **activar**.  

> [!NOTE]
>  Si ya ha activado un acuerdo, haga clic en el nombre del contrato en el panel derecho y, a continuación, haga clic en **Deactivate** para evitar que los mensajes asociados con el acuerdo de envío o recepción.  

## <a name="edit-a-trading-partner-agreement"></a>Editar un acuerdo entre socios comerciales  

1. Haga clic en **Inicio**, elija **Todos los programas**, elija **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Consola de administración**.  

2. En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en el **acuerdos** nodo.  

3. Haga clic en el acuerdo que desea editar y, a continuación, haga clic en **propiedades**.  

4. En el **\<** <em>nombre del contrato</em> **\>** cuadro de diálogo de propiedades el **General** y  **Póngase en contacto con propiedades** fichas, cambiar la configuración según sea necesario. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  

5. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)   
 [Administración de la configuración de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)
