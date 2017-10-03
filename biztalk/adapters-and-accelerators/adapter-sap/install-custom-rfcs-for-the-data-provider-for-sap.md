---
title: Instalar RFC personalizadas para el proveedor de datos para SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation, custom RFCs for the Data Provider for SAP
- installing, custom RFCs for the Data Provider for SAP
- installing custom RFCs, how to
ms.assetid: 7a99db70-fa5a-4c04-9dc7-b71613d4364e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c295834f00781cc92a6aa47d01374c80b485149d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-custom-rfcs-for-the-data-provider-for-sap"></a>Instalar RFC personalizadas para el proveedor de datos para SAP
Instale las RFC personalizadas si desea usar el proveedor de datos de .NET Framework para mySAP Business Suite para tener acceso al sistema SAP.

El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere RFC personalizadas realizar algunas operaciones en el sistema SAP para:
  
-   Ejecutar la operación de selección, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere Z_EXTRACT_DATA_OO RFC.  
  
-   Ejecutar la operación de EXECQUERY el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere Z_EXECUTE_SAP_QUERY RFC.  
  
Para llevar a cabo estas operaciones en el sistema SAP, debe instalar estos RFC personalizadas en el sistema SAP. Si decide instalar la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] junto con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], el programa de instalación copia el transporte RFC para el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] como un archivo comprimido (customRFC.zip) en el sistema donde se instala el adaptador. El archivo zip se instala normalmente en  *\<unidad de instalación >: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft .NET Framework Data Provider para mySAP Business Suite*. 
  
 Después de extraer el archivo zip, encontrará cuatro archivos de datos, dos siguiendo la denominación de patrón K9 *. BI1 (por ejemplo, similar a K900534. BI1) y los otros dos sigue el patrón R9\*. BI1 (por ejemplo, similar a R900534. BI1).  
  

  
1.  Copie los archivos extraídos del equipo que ejecuta los adaptadores para el servidor de aplicaciones de SAP.  
  
    1.  Inicie sesión como el administrador del sistema SAP R/3 al servidor de aplicaciones de SAP de su sistema de desarrollo.  
  
    2.  Copie los archivos de dos transporte con el patrón de nomenclatura K9 *. BI1 desde el directorio de instalación en el equipo que ejecuta los adaptadores en el siguiente directorio en el servidor de aplicaciones de SAP:  
  
         `<drive>:\usr\sap\trans\cofiles`  
  
    3.  Copie los archivos de dos transporte con el patrón de nomenclatura R9 *. BI1 desde el directorio de instalación en el equipo que ejecuta los adaptadores en el siguiente directorio en el servidor de aplicaciones de SAP:  
  
         `<drive>:\usr\sap\trans\data`  
  
2.  Cargar el transporte en el búfer de transporte en el servidor de aplicaciones de SAP.  
  
    1.  En el símbolo del sistema, desplácese al directorio del programa de transporte en el servidor de aplicaciones de SAP:  
  
         `<drive>:\usr\sap\trans\bin`  
  
    2.  Para cargar el transporte en el búfer de transporte, ejecute el comando siguiente en el `\usr\sap\trans\bin` directorio y reemplazar *sysid* con el identificador de sistema de su sistema de desarrollo:  
  
        ```  
        tp addtobuffer <TransportNumber> <sysid> pf=TP_DOMAIN_<sysid>.PFL  
        ```  
  
         WHERE, *TransportNumber* es el número real de transporte (por ejemplo BI1K900534).  
  
    3.  Después de la `tp` comando finalice, verá un informe similar al siguiente:  
  
        ```  
        This is tp version 320.56.66 (release 620)  
        Addtobuffer successful for TransportNumber  
        tp finished with return code: 0  
        ```  
  
         Código de retorno "0" significa que la operación se realizó correctamente.  
  
         Un código de retorno de 0 ó 4 es aceptable. Póngase en contacto con Microsoft servicio y soporte técnico, si recibe un código de retorno de 8 o superior.  
  
        > [!IMPORTANT]
        >  Repita los pasos (b) y (c) para el segundo conjunto de archivos de transporte.  
  
        > [!NOTE]
        >  Puede deducir con facilidad el número real de transporte del nombre de archivo cofile. Por ejemplo, un cofile denominado K900534. BI1 proporciona una serie de transporte de BI1K900534.  
  
3.  Importar el transporte de SAP.  
  
    1.  Ejecute el siguiente comando en el símbolo del sistema:  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL  
        ```  
  
         Reemplace *sysid* con el identificador de sistema de su sistema de desarrollo. Reemplace *clientnumber* con el número de cliente de su sistema de desarrollo.  
  
         Puede utilizar el parámetro U2 para sobrescribir objetos instalados previamente, como se indica a continuación:  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> U2  
        ```  
  
         o bien  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL U2  
        ```  
  
        > [!NOTE]
        >  Puede deducir con facilidad el número real de transporte del nombre de archivo cofile. Por ejemplo, un cofile denominado K900534. BI1 proporciona una serie de transporte de BI1K900534.  
  
    2.  Después de la `tp` comando finalice, verá un informe similar al siguiente:  
  
        ```  
        This is tp version 320.56.66 (release 620)  
        This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
        R3trans.exe finished (0000).  
        This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
        R3trans.exe finished (0000).  
        tp finished with return code: 0  
        ```  
  
         Código de retorno "0" significa que la operación se realizó correctamente.  
  
         Un código de retorno de 0 ó 4 es aceptable. Si recibe un código de retorno de 8 o superior, póngase en contacto con soporte técnico y el servicio de cliente de Microsoft.  
  
        > [!IMPORTANT]
        >  Repita los pasos (a) y (b) para el segundo conjunto de archivos de transporte.  
  
4.  Compruebe el registro de transporte.  
  
5.  Compruebe el registro de transporte en el organizador de transporte de GUI de SAP mediante transacciones SE09 para comprobar que no hay ningún error.  
  
 Configuración de autorización del usuario  
 La solicitud de cambio de Z_EXTRACT_DATA_OO requiere el Id. de usuario con objetos de autorización específica. Use las herramientas de administración de la autorización de GUI de SAP para establecer las restricciones mínimas en la ejecución de la solicitud de cambio:  
  
> [!NOTE]
>  No es necesario establecer la autorización para la solicitud de cambio de Z_EXECUTE_SAP_QUERY.  
  
-   Z_EXTRACT_DATA_OO requiere S_TABU_DIS y Z_EIP_TABL. Los valores siguientes proporcionan las restricciones de mínimas de S_TABU_DIS, lo que permite a los usuarios ver metadatos de las tablas en el sistema.  
  
    -   ACTVT: 03  
  
    -   DICBERCLS: *  
  
     Puede usar DICBERCLS para restringir autorización a las tablas mediante la clase de autorización.  
  
     Puede usar la tabla TDDAT para ver la clase de autorización para las tablas.  
  
    > [!NOTE]
    >  Para evitar cambios en las tablas por las transacciones de mantenimiento de tabla, solo debe conceder privilegios de visualización en un entorno de producción (ACTVT: 03 establece la actividad permitida para mostrar).  
  
     Los valores mínimos de Z_EIP_TABL son:  
  
    -   ACTVT: 03  
  
    -   TABLA: *  
  
     Puede usar la tabla para definir explícitamente las tablas autorizadas. Observe también que S_TABU_DIS también se utiliza en otras transacciones.  
  
##### <a name="to-set-user-authorization"></a>Para establecer la autorización del usuario  
  
1.  Inicie la GUI de SAP. Vaya al código de T, tipo `pfcg`, y presione ENTRAR.  
  
2.  En el **rol** texto cuadro, escriba un nombre de rol que desea crear, por ejemplo, `ZTEST`y, a continuación, haga clic en **rol**.  
  
3.  En el **Create Role** página, haga clic en el **autorizaciones** ficha.  
  
     Si se le pide al guardar el rol, haga clic en **Sí**.  
  
4.  En el **cambiar funciones** página, haga clic en el **datos de autorización de cambio** botón.  
  
5.  Si se le pedirá que seleccione una plantilla en el **Elegir plantilla** cuadro de diálogo, haga clic en **no seleccione plantillas**.  
  
6.  En el **cambio de rol: autorizaciones** página, haga clic en el **manualmente** botón.  
  
7.  En el **selección Manual de autorizaciones** cuadro, escriba el nombre del objeto de autorización `Z_EIP_TABL` y presione ENTRAR.  
  
8.  En el **cambio de rol: autorizaciones** página, expanda los nodos hasta que vea los cuadros de texto para **actividad** y **nombre de la tabla**. Para el **actividad** texto cuadro, escriba el valor `03`. Para el **nombre de la tabla** texto cuadro, escriba el valor `*`.  
  
9. Haga clic en el **guardar** botón para generar el perfil.  
  
10. Vuelva a la **cambiar funciones** página y haga clic en el **usuario** ficha.  
  
11. En el **usuario** ficha, asigne un Id. de usuario para el rol escribiendo el nombre de usuario en el **Id. de usuario** columna y haga clic en el **comparación usuario** botón.  
  
12. En el **comparar el registro de rol de usuario maestro**, haga clic en **completar comparación** para actualizar el registro maestro. Cuando se le pida para guardar el rol, haga clic en **Sí**.  
  
13. Guardar y salir.  
  
Comprobación de la instalación de RFC personalizada  
 Después de instalar las RFC personalizadas, puede comprobar si la RFC se ha instalado correctamente.  
  
-   RFC Z_EXECUTE_SAP_QUERY, puede hacerlo mediante la ejecución de una consulta predefinida en el sistema SAP mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
-   RFC Z_EXTRACT_DATA_OO, puede hacerlo mediante la realización de las siguientes pruebas para confirmar que la RFC funciona y está lista para su uso en el sistema.  
  
##### <a name="to-test-the-installation-of-zextractdataoo"></a>Para probar la instalación de Z_EXTRACT_DATA_OO  
  
1.  En las herramientas de administración de autorización de GUI de SAP, ejecute SE37, módulo de función Z_EXTRACT_DATA_OO, y, a continuación, ejecute la solicitud de cambio en el modo de prueba presionando `F8`. Rellenar los parámetros como se indica a continuación.  
  
    |||  
    |-|-|  
    |IN_METADATA_ONLY||  
    |IN_METADATA_LANGUAGE|EN|  
    |IN_FROM_TABLE|T000|  
    |IN_OUTPUT_MODE|S|  
    |IN_OUTPUT_FILENAME||  
    |IN_USE_FIELD_EXITS|X|  
    |IN_SET_ROWCOUNT|0|  
    |IN_DELIMITER||  
    |IN_PACKET_SIZE|50,000|  
    |IN_MAX_WRITE_ATTEMPTS|4|  
    |IN_RETRY_DELAY|30|  
    |IN_SQL_DATES_ON||  
  
2.  Haga clic en **Execute** o presione `F8`.  
  
3.  En el panel de resultados, compruebe lo siguiente.  
  
    |||  
    |-|-|  
    |OUT_TABLEHEADER|\<Metadatos generales T000 >|  
    |OUT_TECHNICALSETTINGS|\<Los metadatos de nivel de base de datos técnica T000 >|  
    |OUT_RECORDLENGTH|\<depende de versión SAP >|  
    |OUT_RECORDCOUNT|\<Confirme el número de clientes en el sistema con SE16 en T000 >|  
    |OUT_ZDATATABLE|\<confirmar este resultado con los datos de origen con 16 SAR en T000 >|  
    |OUT_RETURN_TAB|S 001 correcto|  
  
## <a name="remove-the-rfc-for-the-data-provider-for-sap"></a>Quite la solicitud de cambio para el proveedor de datos para SAP  
  
1.  En el Explorador de objetos de GUI de SAP (SE80), busque todos los objetos con la clase de desarrollo ZMSBI.  
  
2.  Eliminar todos los objetos con la clase de desarrollo ZMSBI de las siguientes carpetas de objetos de diccionario:  
  
    -   Estructuras  
  
    -   Grupos de funciones  
  
    -   Objeto autorizado  
  
3.  Generar un transporte y migrar a través de cada sistema donde se instaló una solicitud de cambio (por ejemplo, los sistemas desarrollo, prueba y producción).  
  
     Para obtener más ayuda, póngase en contacto con el Administrador de base de SAP.  
     
## <a name="next"></a>Siguiente
[Comprender el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)  
[Tutoriales del adaptador SAP](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)