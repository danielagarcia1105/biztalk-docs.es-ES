---
title: "Configuración de juego de caracteres y separadores (X12) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6249f2e1-70b0-4960-bbc4-0c3fefd26faa
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43e32c4d9a240c3302126fc403d64efd787ed54c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-charset-and-separators-x12"></a>Configuración de juego de caracteres y separadores (X12)
En el acuerdo de socios comerciales, puede especificar el juego de caracteres que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para validar las propiedades de entidad al crear el sobre para un mensaje X12 saliente. También puede especificar los separadores y terminadores que se usarán para los segmentos del intercambio.  
  
> [!NOTE]
>  La configuración descrita aquí también se aplica a los intercambios HIPAA.  
  
> [!IMPORTANT]
>  Las propiedades siguientes están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
>   
>  -   **Elemento de datos**  
> -   **Separador de elementos de componente (ISA16)**  
> -   **Terminador de segmento**  
> -   **Sufijo**  
> -   **Reemplazar separadores de carga con**  
>   
>  Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-character-set-and-separators"></a>Para configurar el juego de caracteres y los separadores  
  
1.  Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **juego de caracteres y separadores**.  
  
3.  Desde el **juego de caracteres que se utilizará** lista desplegable, seleccione el X12 juego de caracteres que se usa para validar las propiedades que especifique para el acuerdo.  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo usa esta configuración para validar los valores especificados para las propiedades de contrato relacionadas. La canalización de recepción o la de envío hará caso omiso de esta propiedad de juego de caracteres al realizar el procesamiento en tiempo de ejecución.  
  
4.  Para **elemento de datos**, especifique un único carácter que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para separar elementos de datos compuestos que consten de dos o más elementos de datos simples y los elementos de datos simples que no forman parte de un elemento compuesto. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambiará automáticamente cuando se cambia el formato de **Char** a **hexadecimal** o viceversa.  
  
5.  Para **separador de elementos de componente (ISA16)**, especifique un único carácter que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para separar elementos de datos simples dentro de los elementos de datos compuestos. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambiará automáticamente cuando se cambia el formato de **Char** a **hexadecimal** o viceversa.  
  
6.  Para **terminador de segmento**, escriba un único carácter para indicar el final de un segmento EDI. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales.  
  
     Si el tipo es **Char**, el valor predeterminado es  **~** .  
  
     Si el tipo es **hexadecimal**, el valor predeterminado es **7E**.  
  
     Este elemento de datos es necesario.  
  
     Este elemento está limitado a los valores del juego de caracteres ASCII. Esta propiedad no se valida con respecto al juego de caracteres X12 definido en la página General.  
  
     El carácter que escriba cambiará automáticamente cuando se cambia el formato de **Char** a **hexadecimal** o viceversa.  
  
7.  Para **sufijo**, seleccione el carácter que se va a usar **con** el valor de terminador de segmento. Las opciones son:  
  
    -   **Ninguno**: predeterminado  
  
    -   **CR**: retorno de carro  
  
    -   **LF**: avance de línea  
  
    -   **CR LF**: / línea de retorno de carro, avance  
  
     Entre las combinaciones de Terminador de segmento y Sufijo se incluyen las siguientes:  
  
    -   **Cualquier** terminador de segmento + **ninguno** sufijo  
  
    -   **Cualquier** terminador de segmento + **CR** sufijo  
  
    -   **Cualquier** terminador de segmento + **CR LF** sufijo  
  
    -   **D. (Hex)** terminador de segmento + **ninguno** sufijo: esta combinación se comporta como si estuviera en blanco terminador de segmento y sufijo se hubiera definido como CR.  
  
    -   Un terminador de segmento (Hex) + **ninguno** sufijo: esta combinación se comporta como si estuviera en blanco terminador de segmento y sufijo se hubiera definido como LF.  
  
    -   **D. (Hex)** terminador de segmento + **LF** sufijo: esta combinación se comporta como si terminador de segmento es CR y sufijo se hubiera definido como LF.  
  
8.  Si los datos de carga contienen caracteres que también se usan como datos, segmentos o separadores de componentes, consulte **reemplazar separadores de carga con** y especificar un carácter de reemplazo. Al generar el mensaje X12 de salida, todas las instancias de caracteres de separador en los datos de carga se sustituirán por el carácter especificado. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambiará automáticamente cuando se cambia el formato de **Char** a **hexadecimal** o viceversa.  
  
9. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de intercambio (X12)](../core/configuring-interchange-settings-x12.md)