from building import *
import os

cwd = GetCurrentDir()
path = [os.path.join(cwd, 'n32h47x_48x_std_periph_driver/inc')]

src_path = os.path.join(cwd, 'n32h47x_48x_std_periph_driver/src')

# Select library file
src = [
os.path.join(src_path, 'misc.c'),
os.path.join(src_path, 'n32h47x_48x_gpio.c'),
os.path.join(src_path, 'n32h47x_48x_dma.c'),
os.path.join(src_path, 'n32h47x_48x_pwr.c'),
os.path.join(src_path, 'n32h47x_48x_rcc.c'),
os.path.join(src_path, 'n32h47x_48x_dbg.c'),
os.path.join(src_path, 'n32h47x_48x_exti.c'),
]

if GetDepend(['RT_USING_SERIAL']) or GetDepend(['RT_USING_NANO', 'RT_USING_CONSOLE']):
    src += [os.path.join(src_path, 'n32h47x_48x_usart.c')]

if GetDepend(['RT_USING_HWTIMER']) or GetDepend(['RT_USING_PWM']) or GetDepend(['RT_USING_PULSE_ENCODER']):
    src += [os.path.join(src_path, 'n32h47x_48x_tim.c')]
    
if GetDepend(['RT_USING_SPI']):
    src += [os.path.join(src_path, 'n32h47x_48x_spi.c')]

if GetDepend(['RT_USING_QSPI']):
    src += [os.path.join(src_path, 'n32h47x_48x_xspi.c')]

if GetDepend(['RT_USING_I2C']):
    src += [os.path.join(src_path, 'n32h47x_48x_i2c.c')]

if GetDepend(['BSP_USING_ETH']):
    src += [os.path.join(src_path, 'n32h47x_48x_eth.c')]

if GetDepend(['RT_USING_ADC']):
    src += [os.path.join(src_path, 'n32h47x_48x_adc.c')]

if GetDepend(['RT_USING_DAC']):
    src += [os.path.join(src_path, 'n32h47x_48x_dac.c')]

if GetDepend(['RT_USING_CAN']):
    src += [os.path.join(src_path, 'n32h47x_48x_fdcan.c')]

if GetDepend(['RT_USING_PM']):
    src += [os.path.join(src_path, 'n32h47x_48x_pwr.c')]

if GetDepend(['BSP_USING_LPTIM']):
    src += [os.path.join(src_path, 'n32h47x_48x_lptim.c')]

if GetDepend(['RT_USING_RTC']):
    src += [os.path.join(src_path, 'n32h47x_48x_rtc.c')]

if GetDepend(['BSP_USING_ON_CHIP_FLASH']):
    src += [os.path.join(src_path, 'n32h47x_48x_flash.c')]

if GetDepend(['RT_USING_WDT']):
    src += [os.path.join(src_path, 'n32h47x_48x_iwdg.c')]
    src += [os.path.join(src_path, 'n32h47x_48x_wwdg.c')]

if GetDepend(['RT_USING_SDIO']):
    src += [os.path.join(src_path, 'n32h47x_48x_sdio.c')]

if GetDepend(['RT_USING_MTD_NAND']) or GetDepend(['RT_USING_MTD_NOR']) or GetDepend(['BSP_USING_NAND']):
    src += [os.path.join(src_path, 'n32h47x_48x_femc.c')]

if GetDepend(['BSP_USING_CLOCK_TIMER']) or GetDepend(['BSP_USING_PWM']) :
    src += [os.path.join(src_path, 'n32h47x_48x_tim.c')]


CPPDEFINES = ['USE_STDPERIPH_DRIVER']

group = DefineGroup('Libraries', src, depend = ['PKG_USING_N32H47X_48X_STD_DRIVER'], CPPPATH = path, CPPDEFINES = CPPDEFINES)

Return('group')
