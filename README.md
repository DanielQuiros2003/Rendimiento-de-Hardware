# Rendimiento-de-Hardware
import psutil
import platform
import os
import speedtest

def get_cpu_usage():
    return psutil.cpu_percent(interval=1)

def get_memory_usage():
    return psutil.virtual_memory().percent

def get_network_speed():
    st = speedtest.Speedtest()
    return st.download() / 1024 / 1024  # Descarga en Mbps

def get_cpu_temperature():
    # Puedes implementar esta función utilizando herramientas específicas para tu sistema operativo
    # Por ejemplo, para Linux, podrías leer el archivo /sys/class/thermal/thermal_zone0/temp
    # Consulta la documentación de la herramienta que estás utilizando para obtener la temperatura del CPU.
    # Ten en cuenta que no todos los sistemas proporcionan esta información de la misma manera.
    return "No disponible"

def main():
    print(f"Sistema operativo: {platform.system()} {platform.version()}")
    print(f"USO DE CPU: {get_cpu_usage()}%")
    print(f"USO DE MEMORIA: {get_memory_usage()}%")
    print(f"VELOCIDAD DE RED: {get_network_speed():.2f} Mbps")
    print(f"CPU Temperatura: {get_cpu_temperature()}")

if _name_ == "_main_":
    main()
