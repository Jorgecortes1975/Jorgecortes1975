<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Balance PYME Colombia</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .gradient-bg {
            background: linear-gradient(135deg, #1e3a8a 0%, #1e40af 100%);
        }
        .card-hover:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        .input-highlight:focus {
            border-color: #3b82f6;
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.3);
        }
        .pulse {
            animation: pulse 2s infinite;
        }
        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
            100% {
                transform: scale(1);
            }
        }
    </style>
</head>
<body class="bg-gray-50 min-h-screen">
    <header class="gradient-bg text-white shadow-lg">
        <div class="container mx-auto px-4 py-6">
            <div class="flex justify-between items-center">
                <div class="flex items-center space-x-3">
                    <i class="fas fa-chart-line text-3xl"></i>
                    <h1 class="text-2xl font-bold">Balance PYME Colombia</h1>
                </div>
                <div class="hidden md:flex items-center space-x-4">
                    <a href="#calculadora" class="hover:text-blue-200 transition">Calculadora</a>
                    <a href="#resultados" class="hover:text-blue-200 transition">Resultados</a>
                    <a href="#ahorro" class="hover:text-blue-200 transition">Plan de Ahorro</a>
                </div>
                <button class="md:hidden text-xl">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>
    </header>

    <main class="container mx-auto px-4 py-8">
        <!-- Sección de bienvenida -->
        <section class="mb-12 text-center">
            <div class="max-w-3xl mx-auto">
                <h2 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">Gestión Financiera para tu PYME</h2>
                <p class="text-lg text-gray-600 mb-6">Calcula tu balance mensual, analiza tu rentabilidad y descubre cómo optimizar tus finanzas con nuestro plan de ahorro inteligente.</p>
                <div class="flex justify-center space-x-4">
                    <a href="#calculadora" class="bg-blue-600 hover:bg-blue-700 text-white px-6 py-3 rounded-lg font-medium transition transform hover:scale-105">
                        Comenzar <i class="fas fa-arrow-down ml-2"></i>
                    </a>
                    <a href="#tutorial" class="bg-gray-200 hover:bg-gray-300 text-gray-800 px-6 py-3 rounded-lg font-medium transition">
                        <i class="fas fa-question-circle mr-2"></i> Cómo funciona
                    </a>
                </div>
            </div>
        </section>

        <!-- Calculadora -->
        <section id="calculadora" class="mb-16">
            <div class="bg-white rounded-xl shadow-lg overflow-hidden">
                <div class="gradient-bg px-6 py-4">
                    <h2 class="text-xl font-bold text-white flex items-center">
                        <i class="fas fa-calculator mr-3"></i> Calculadora Financiera
                    </h2>
                </div>
                <div class="p-6">
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                        <!-- Ingresos -->
                        <div class="bg-blue-50 p-5 rounded-lg border border-blue-100 card-hover transition">
                            <h3 class="text-lg font-semibold text-blue-800 mb-4 flex items-center">
                                <i class="fas fa-money-bill-wave mr-2"></i> Ingresos
                            </h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Ventas</label>
                                    <div class="relative">
                                        <span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
                                        <input type="number" id="ventas" class="pl-8 w-full rounded-md border-gray-300 shadow-sm input-highlight" placeholder="0">
                                    </div>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Otros ingresos</label>
                                    <div class="relative">
                                        <span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
                                        <input type="number" id="otros-ingresos" class="pl-8 w-full rounded-md border-gray-300 shadow-sm input-highlight" placeholder="0">
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Costos -->
                        <div class="bg-red-50 p-5 rounded-lg border border-red-100 card-hover transition">
                            <h3 class="text-lg font-semibold text-red-800 mb-4 flex items-center">
                                <i class="fas fa-tags mr-2"></i> Costos
                            </h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Costo de ventas</label>
                                    <div class="relative">
                                        <span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
                                        <input type="number" id="costo-ventas" class="pl-8 w-full rounded-md border-gray-300 shadow-sm input-highlight" placeholder="0">
                                    </div>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Materia prima</label>
                                    <div class="relative">
                                        <span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
                                        <input type="number" id="materia-prima" class="pl-8 w-full rounded-md border-gray-300 shadow-sm input-highlight" placeholder="0">
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Gastos -->
                        <div class="bg-yellow-50 p-5 rounded-lg border border-yellow-100 card-hover transition">
                            <h3 class="text-lg font-semibold text-yellow-800 mb-4 flex items-center">
                                <i class="fas fa-receipt mr-2"></i> Gastos
                            </h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Gastos operativos</label>
                                    <div class="relative">
                                        <span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
                                        <input type="number" id="gastos-operativos" class="pl-8 w-full rounded-md border-gray-300 shadow-sm input-highlight" placeholder="0">
                                    </div>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Gastos administrativos</label>
                                    <div class="relative">
                                        <span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
                                        <input type="number" id="gastos-administrativos" class="pl-8 w-full rounded-md border-gray-300 shadow-sm input-highlight" placeholder="0">
                                    </div>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-1">Impuestos</label>
                                    <div class="relative">
                                        <span class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-500">$</span>
                                        <input type="number" id="impuestos" class="pl-8 w-full rounded-md border-gray-300 shadow-sm input-highlight" placeholder="0">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="mt-6 flex justify-center">
                        <button id="calcular-btn" class="gradient-bg hover:opacity-90 text-white px-8 py-3 rounded-lg font-medium transition transform hover:scale-105 pulse">
                            <i class="fas fa-calculator mr-2"></i> Calcular Balance
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Resultados -->
        <section id="resultados" class="mb-16 hidden">
            <div class="bg-white rounded-xl shadow-lg overflow-hidden">
                <div class="gradient-bg px-6 py-4">
                    <h2 class="text-xl font-bold text-white flex items-center">
                        <i class="fas fa-chart-pie mr-3"></i> Resultados Financieros
                    </h2>
                </div>
                <div class="p-6">
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-8">
                        <!-- Resumen -->
                        <div class="bg-white border border-gray-200 rounded-lg p-5 shadow-sm card-hover transition">
                            <h3 class="text-lg font-semibold text-gray-800 mb-4 flex items-center">
                                <i class="fas fa-file-invoice-dollar mr-2 text-blue-600"></i> Resumen Mensual
                            </h3>
                            <div class="space-y-3">
                                <div class="flex justify-between border-b pb-2">
                                    <span class="text-gray-600">Total Ingresos:</span>
                                    <span id="total-ingresos" class="font-medium text-green-600">$0</span>
                                </div>
                                <div class="flex justify-between border-b pb-2">
                                    <span class="text-gray-600">Total Costos:</span>
                                    <span id="total-costos" class="font-medium text-red-600">$0</span>
                                </div>
                                <div class="flex justify-between border-b pb-2">
                                    <span class="text-gray-600">Total Gastos:</span>
                                    <span id="total-gastos" class="font-medium text-yellow-600">$0</span>
                                </div>
                                <div class="flex justify-between pt-2">
                                    <span class="text-gray-800 font-medium">Utilidad Neta:</span>
                                    <span id="utilidad-neta" class="font-bold text-lg text-blue-600">$0</span>
                                </div>
                            </div>
                        </div>

                        <!-- Margenes -->
                        <div class="bg-white border border-gray-200 rounded-lg p-5 shadow-sm card-hover transition">
                            <h3 class="text-lg font-semibold text-gray-800 mb-4 flex items-center">
                                <i class="fas fa-percent mr-2 text-purple-600"></i> Margenes
                            </h3>
                            <div class="space-y-3">
                                <div class="flex justify-between border-b pb-2">
                                    <span class="text-gray-600">Margen Bruto:</span>
                                    <span id="margen-bruto" class="font-medium text-purple-600">0%</span>
                                </div>
                                <div class="flex justify-between border-b pb-2">
                                    <span class="text-gray-600">Margen Operativo:</span>
                                    <span id="margen-operativo" class="font-medium text-purple-600">0%</span>
                                </div>
                                <div class="flex justify-between border-b pb-2">
                                    <span class="text-gray-600">Margen Neto:</span>
                                    <span id="margen-neto" class="font-medium text-purple-600">0%</span>
                                </div>
                                <div class="pt-4">
                                    <div class="h-2 bg-gray-200 rounded-full overflow-hidden">
                                        <div id="margen-bar" class="h-full bg-gradient-to-r from-purple-400 to-purple-600 rounded-full" style="width: 0%"></div>
                                    </div>
                                    <p class="text-xs text-gray-500 mt-1">Eficiencia operativa</p>
                                </div>
                            </div>
                        </div>

                        <!-- Recomendación -->
                        <div class="bg-white border border-gray-200 rounded-lg p-5 shadow-sm card-hover transition">
                            <h3 class="text-lg font-semibold text-gray-800 mb-4 flex items-center">
                                <i class="fas fa-lightbulb mr-2 text-green-600"></i> Recomendación Inicial
                            </h3>
                            <div id="recomendacion-inicial" class="text-gray-700">
                                <p class="text-sm">Ingresa tus datos financieros para obtener recomendaciones personalizadas para tu PYME.</p>
                            </div>
                            <div class="mt-4">
                                <div class="flex items-center">
                                    <div class="flex-shrink-0 h-8 w-8 rounded-full bg-green-100 flex items-center justify-center">
                                        <i class="fas fa-check text-green-600"></i>
                                    </div>
                                    <div class="ml-3">
                                        <p id="recomendacion-item-1" class="text-sm text-gray-600">-</p>
                                    </div>
                                </div>
                                <div class="flex items-center mt-2">
                                    <div class="flex-shrink-0 h-8 w-8 rounded-full bg-green-100 flex items-center justify-center">
                                        <i class="fas fa-check text-green-600"></i>
                                    </div>
                                    <div class="ml-3">
                                        <p id="recomendacion-item-2" class="text-sm text-gray-600">-</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Gráfico -->
                    <div class="bg-gray-50 p-6 rounded-lg border border-gray-200">
                        <h3 class="text-lg font-semibold text-gray-800 mb-4">Distribución Financiera</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                            <div>
                                <canvas id="financesChart" height="250"></canvas>
                            </div>
                            <div class="flex items-center">
                                <div class="w-full">
                                    <div class="flex items-center mb-2">
                                        <div class="w-4 h-4 bg-blue-500 rounded-full mr-2"></div>
                                        <span class="text-sm text-gray-700">Ingresos</span>
                                        <span id="chart-ingresos" class="ml-auto font-medium">$0</span>
                                    </div>
                                    <div class="flex items-center mb-2">
                                        <div class="w-4 h-4 bg-red-500 rounded-full mr-2"></div>
                                        <span class="text-sm text-gray-700">Costos</span>
                                        <span id="chart-costos" class="ml-auto font-medium">$0</span>
                                    </div>
                                    <div class="flex items-center mb-2">
                                        <div class="w-4 h-4 bg-yellow-500 rounded-full mr-2"></div>
                                        <span class="text-sm text-gray-700">Gastos</span>
                                        <span id="chart-gastos" class="ml-auto font-medium">$0</span>
                                    </div>
                                    <div class="flex items-center mb-2">
                                        <div class="w-4 h-4 bg-green-500 rounded-full mr-2"></div>
                                        <span class="text-sm text-gray-700">Utilidad Neta</span>
                                        <span id="chart-utilidad" class="ml-auto font-medium">$0</span>
                                    </div>
                                    <div class="mt-4 pt-4 border-t">
                                        <p class="text-sm text-gray-600">Este análisis te ayuda a visualizar cómo se distribuyen tus recursos y dónde podrías optimizar.</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Plan de Ahorro -->
        <section id="ahorro" class="hidden">
            <div class="bg-white rounded-xl shadow-lg overflow-hidden">
                <div class="gradient-bg px-6 py-4">
                    <h2 class="text-xl font-bold text-white flex items-center">
                        <i class="fas fa-piggy-bank mr-3"></i> Plan de Ahorro Inteligente
                    </h2>
                </div>
                <div class="p-6">
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Objetivo de ahorro mensual sugerido:</h3>
                        <div class="bg-blue-50 border border-blue-200 rounded-lg p-4">
                            <div class="flex items-center justify-between">
                                <div>
                                    <p class="text-blue-800 font-medium">Meta recomendada:</p>
                                    <p id="meta-ahorro" class="text-2xl font-bold text-blue-600">$0</p>
                                </div>
                                <div class="bg-blue-100 p-3 rounded-full">
                                    <i class="fas fa-bullseye text-blue-600 text-2xl"></i>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
                        <!-- Estrategias -->
                        <div class="bg-white border border-gray-200 rounded-lg p-5 shadow-sm">
                            <h3 class="text-lg font-semibold text-gray-800 mb-4 flex items-center">
                                <i class="fas fa-chess-knight mr-2 text-indigo-600"></i> Estrategias de Ahorro
                            </h3>
                            <div id="estrategias-ahorro" class="space-y-4">
                                <div class="flex items-start">
                                    <div class="flex-shrink-0 h-6 w-6 rounded-full bg-indigo-100 flex items-center justify-center mt-1">
                                        <i class="fas fa-check text-indigo-600 text-xs"></i>
                                    </div>
                                    <div class="ml-3">
                                        <p class="text-sm font-medium text-gray-800">Optimiza tus compras de materia prima</p>
                                        <p class="text-xs text-gray-500">Negocia con proveedores o busca alternativas más económicas</p>
                                    </div>
                                </div>
                                <div class="flex items-start">
                                    <div class="flex-shrink-0 h-6 w-6 rounded-full bg-indigo-100 flex items-center justify-center mt-1">
                                        <i class="fas fa-check text-indigo-600 text-xs"></i>
                                    </div>
                                    <div class="ml-3">
                                        <p class="text-sm font-medium text-gray-800">Reduce gastos operativos innecesarios</p>
                                        <p class="text-xs text-gray-500">Analiza qué gastos pueden ser recortados sin afectar operaciones</p>
                                    </div>
                                </div>
                                <div class="flex items-start">
                                    <div class="flex-shrink-0 h-6 w-6 rounded-full bg-indigo-100 flex items-center justify-center mt-1">
                                        <i class="fas fa-check text-indigo-600 text-xs"></i>
                                    </div>
                                    <div class="ml-3">
                                        <p class="text-sm font-medium text-gray-800">Automatiza procesos</p>
                                        <p class="text-xs text-gray-500">Invierte en tecnología que reduzca costos a largo plazo</p>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- Proyección -->
                        <div class="bg-white border border-gray-200 rounded-lg p-5 shadow-sm">
                            <h3 class="text-lg font-semibold text-gray-800 mb-4 flex items-center">
                                <i class="fas fa-chart-line mr-2 text-teal-600"></i> Proyección de Ahorro
                            </h3>
                            <div class="space-y-3">
                                <div class="flex justify-between">
                                    <span class="text-gray-600">En 3 meses:</span>
                                    <span id="ahorro-3meses" class="font-medium text-teal-600">$0</span>
                                </div>
                                <div class="flex justify-between">
                                    <span class="text-gray-600">En 6 meses:</span>
                                    <span id="ahorro-6meses" class="font-medium text-teal-600">$0</span>
                                </div>
                                <div class="flex justify-between">
                                    <span class="text-gray-600">En 1 año:</span>
                                    <span id="ahorro-1ano" class="font-medium text-teal-600">$0</span>
                                </div>
                            </div>
                            <div class="mt-4">
                                <canvas id="savingsChart" height="150"></canvas>
                            </div>
                        </div>
                    </div>

                    <div class="bg-green-50 border border-green-200 rounded-lg p-5">
                        <h3 class="text-lg font-semibold text-green-800 mb-3 flex items-center">
                            <i class="fas fa-rocket mr-2"></i> Plan de Acción
                        </h3>
                        <p class="text-sm text-gray-700 mb-4">Basado en tu balance mensual, te sugerimos el siguiente plan para mejorar tu salud financiera:</p>
                        
                        <div id="plan-accion" class="space-y-3">
                            <!-- Aquí se generará el plan de acción dinámicamente -->
                        </div>

                        <div class="mt-6">
                            <button id="descargar-plan-btn" class="bg-green-600 hover:bg-green-700 text-white px-6 py-2 rounded-lg font-medium transition flex items-center">
                                <i class="fas fa-file-pdf mr-2"></i> Descargar Plan Completo
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tutorial -->
        <section id="tutorial" class="mt-16 bg-gray-50 rounded-xl p-6 border border-gray-200">
            <h2 class="text-2xl font-bold text-gray-800 mb-6 flex items-center">
                <i class="fas fa-question-circle text-blue-600 mr-3"></i> ¿Cómo usar esta herramienta?
            </h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="bg-white p-5 rounded-lg shadow-sm card-hover transition">
                    <div class="flex items-center mb-3">
                        <div class="bg-blue-100 p-2 rounded-full mr-3">
                            <i class="fas fa-pen text-blue-600"></i>
                        </div>
                        <h3 class="font-semibold text-gray-800">Paso 1: Ingresa tus datos</h3>
                    </div>
                    <p class="text-sm text-gray-600">Completa todos los campos en la sección de ingresos, costos y gastos con los valores correspondientes a tu último mes de operación.</p>
                </div>
                <div class="bg-white p-5 rounded-lg shadow-sm card-hover transition">
                    <div class="flex items-center mb-3">
                        <div class="bg-purple-100 p-2 rounded-full mr-3">
                            <i class="fas fa-calculator text-purple-600"></i>
                        </div>
                        <h3 class="font-semibold text-gray-800">Paso 2: Calcula tu balance</h3>
                    </div>
                    <p class="text-sm text-gray-600">Haz clic en el botón "Calcular Balance" para obtener un análisis detallado de tu situación financiera.</p>
                </div>
                <div class="bg-white p-5 rounded-lg shadow-sm card-hover transition">
                    <div class="flex items-center mb-3">
                        <div class="bg-green-100 p-2 rounded-full mr-3">
                            <i class="fas fa-lightbulb text-green-600"></i>
                        </div>
                        <h3 class="font-semibold text-gray-800">Paso 3: Implementa las recomendaciones</h3>
                    </div>
                    <p class="text-sm text-gray-600">Revisa el plan de ahorro sugerido y las estrategias para mejorar la rentabilidad de tu negocio.</p>
                </div>
            </div>
        </section>
    </main>

    <footer class="gradient-bg text-white py-8 mt-12">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div>
                    <h3 class="text-lg font-semibold mb-4 flex items-center">
                        <i class="fas fa-balance-scale mr-2"></i> Balance PYME Colombia
                    </h3>
                    <p class="text-sm text-blue-100">Herramienta diseñada para ayudar a las pequeñas y medianas empresas en Colombia a gestionar sus finanzas de manera efectiva.</p>
                </div>
                <div>
                    <h3 class="text-lg font-semibold mb-4">Enlaces útiles</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-blue-100 hover:text-white transition">DIAN - Impuestos</a></li>
                        <li><a href="#" class="text-blue-100 hover:text-white transition">Cámara de Comercio</a></li>
                        <li><a href="#" class="text-blue-100 hover:text-white transition">Ministerio de Comercio</a></li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold mb-4">Contáctanos</h3>
                    <div class="flex items-center mb-2">
                        <i class="fas fa-envelope mr-2 text-blue-200"></i>
                        <span class="text-sm text-blue-100">info@pymecolombia.com</span>
                    </div>
                    <div class="flex items-center">
                        <i class="fas fa-phone mr-2 text-blue-200"></i>
                        <span class="text-sm text-blue-100">+57 1 234 5678</span>
                    </div>
                </div>
            </div>
            <div class="border-t border-blue-400 mt-8 pt-6 text-center text-sm text-blue-100">
                <p>© 2023 Balance PYME Colombia. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Elementos del DOM
            const calcularBtn = document.getElementById('calcular-btn');
            const resultadosSection = document.getElementById('resultados');
            const ahorroSection = document.getElementById('ahorro');
            
            // Variables para los gráficos
            let financesChart = null;
            let savingsChart = null;

            // Formatear números como dinero
            function formatMoney(amount) {
                return '$' + amount.toFixed(0).replace(/\d(?=(\d{3})+$)/g, '$&.');
            }

            // Formatear porcentajes
            function formatPercent(amount) {
                return amount.toFixed(1) + '%';
            }

            // Calcular balance
            calcularBtn.addEventListener('click', function() {
                // Obtener valores de los inputs
                const ventas = parseFloat(document.getElementById('ventas').value) || 0;
                const otrosIngresos = parseFloat(document.getElementById('otros-ingresos').value) || 0;
                const costoVentas = parseFloat(document.getElementById('costo-ventas').value) || 0;
                const materiaPrima = parseFloat(document.getElementById('materia-prima').value) || 0;
                const gastosOperativos = parseFloat(document.getElementById('gastos-operativos').value) || 0;
                const gastosAdministrativos = parseFloat(document.getElementById('gastos-administrativos').value) || 0;
                const impuestos = parseFloat(document.getElementById('impuestos').value) || 0;

                // Calcular totales
                const totalIngresos = ventas + otrosIngresos;
                const totalCostos = costoVentas + materiaPrima;
                const totalGastos = gastosOperativos + gastosAdministrativos + impuestos;
                const utilidadBruta = totalIngresos - totalCostos;
                const utilidadOperativa = utilidadBruta - gastosOperativos - gastosAdministrativos;
                const utilidadNeta = utilidadOperativa - impuestos;

                // Calcular márgenes
                const margenBruto = (utilidadBruta / totalIngresos) * 100;
                const margenOperativo = (utilidadOperativa / totalIngresos) * 100;
                const margenNeto = (utilidadNeta / totalIngresos) * 100;

                // Mostrar resultados
                document.getElementById('total-ingresos').textContent = formatMoney(totalIngresos);
                document.getElementById('total-costos').textContent = formatMoney(totalCostos);
                document.getElementById('total-gastos').textContent = formatMoney(totalGastos);
                document.getElementById('utilidad-neta').textContent = formatMoney(utilidadNeta);
                
                document.getElementById('margen-bruto').textContent = formatPercent(margenBruto);
                document.getElementById('margen-operativo').textContent = formatPercent(margenOperativo);
                document.getElementById('margen-neto').textContent = formatPercent(margenNeto);
                
                // Actualizar barra de margen
                const margenBar = document.getElementById('margen-bar');
                margenBar.style.width = Math.min(margenNeto, 100) + '%';

                // Generar recomendaciones
                generarRecomendaciones(utilidadNeta, margenNeto, totalGastos);

                // Mostrar secciones ocultas
                resultadosSection.classList.remove('hidden');
                ahorroSection.classList.remove('hidden');

                // Scroll a resultados
                resultadosSection.scrollIntoView({ behavior: 'smooth' });

                // Actualizar gráficos
                actualizarGraficos(totalIngresos, totalCostos, totalGastos, utilidadNeta);
                generarPlanAhorro(utilidadNeta, totalGastos);
            });

            // Generar recomendaciones basadas en los resultados
            function generarRecomendaciones(utilidadNeta, margenNeto, totalGastos) {
                const recomendacionInicial = document.getElementById('recomendacion-inicial');
                const item1 = document.getElementById('recomendacion-item-1');
                const item2 = document.getElementById('recomendacion-item-2');
                
                if (utilidadNeta <= 0) {
                    recomendacionInicial.innerHTML = '<p class="text-red-600 font-medium">Tu negocio está operando con pérdidas. Es crucial tomar medidas inmediatas para mejorar la rentabilidad.</p>';
                    item1.textContent = 'Revisa tus costos fijos y busca formas de reducirlos';
                    item2.textContent = 'Considera aumentar precios o buscar nuevos mercados';
                } else if (margenNeto < 10) {
                    recomendacionInicial.innerHTML = '<p class="text-yellow-600 font-medium">Tu negocio es rentable, pero con márgenes bajos. Hay oportunidades para mejorar.</p>';
                    item1.textContent = 'Optimiza tus procesos para reducir gastos operativos';
                    item2.textContent = 'Analiza si puedes aumentar precios sin perder clientes';
                } else {
                    recomendacionInicial.innerHTML = '<p class="text-green-600 font-medium">¡Buen trabajo! Tu negocio tiene márgenes saludables. Sigue así.</p>';
                    item1.textContent = 'Considera reinvertir parte de las utilidades para crecer';
                    item2.textContent = 'Diversifica tus fuentes de ingreso para reducir riesgos';
                }
            }

            // Actualizar gráficos financieros
            function actualizarGraficos(ingresos, costos, gastos, utilidad) {
                // Datos para el gráfico circular
                const ctx = document.getElementById('financesChart').getContext('2d');
                
                // Destruir gráfico anterior si existe
                if (financesChart) {
                    financesChart.destroy();
                }
                
                financesChart = new Chart(ctx, {
                    type: 'doughnut',
                    data: {
                        labels: ['Ingresos', 'Costos', 'Gastos', 'Utilidad Neta'],
                        datasets: [{
                            data: [ingresos, costos, gastos, utilidad],
                            backgroundColor: [
                                '#3b82f6',
                                '#ef4444',
                                '#f59e0b',
                                '#10b981'
                            ],
                            borderWidth: 1
                        }]
                    },
                    options: {
                        responsive: true,
                        plugins: {
                            legend: {
                                position: 'right',
                            },
                            tooltip: {
                                callbacks: {
                                    label: function(context) {
                                        let label = context.label || '';
                                        if (label) {
                                            label += ': ';
                                        }
                                        label += formatMoney(context.raw);
                                        return label;
                                    }
                                }
                            }
                        }
                    }
                });

                // Actualizar leyenda del gráfico
                document.getElementById('chart-ingresos').textContent = formatMoney(ingresos);
                document.getElementById('chart-costos').textContent = formatMoney(costos);
                document.getElementById('chart-gastos').textContent = formatMoney(gastos);
                document.getElementById('chart-utilidad').textContent = formatMoney(utilidad);
            }

            // Generar plan de ahorro
            function generarPlanAhorro(utilidadNeta, totalGastos) {
                // Calcular meta de ahorro (20% de la utilidad o 5% de gastos si hay pérdidas)
                let metaAhorro = utilidadNeta > 0 ? utilidadNeta * 0.2 : totalGastos * 0.05;
                
                // Mostrar meta de ahorro
                document.getElementById('meta-ahorro').textContent = formatMoney(metaAhorro);
                
                // Calcular proyecciones
                document.getElementById('ahorro-3meses').textContent = formatMoney(metaAhorro * 3);
                document.getElementById('ahorro-6meses').textContent = formatMoney(metaAhorro * 6);
                document.getElementById('ahorro-1ano').textContent = formatMoney(metaAhorro * 12);
                
                // Actualizar gráfico de ahorro
                const ctxSavings = document.getElementById('savingsChart').getContext('2d');
                
                // Destruir gráfico anterior si existe
                if (savingsChart) {
                    savingsChart.destroy();
                }
                
                savingsChart = new Chart(ctxSavings, {
                    type: 'line',
                    data: {
                        labels: ['Ahora', '3 meses', '6 meses', '1 año'],
                        datasets: [{
                            label: 'Ahorro acumulado',
                            data: [0, metaAhorro * 3, metaAhorro * 6, metaAhorro * 12],
                            backgroundColor: 'rgba(16, 185, 129, 0.1)',
                            borderColor: '#10b981',
                            borderWidth: 2,
                            tension: 0.4,
                            fill: true
                        }]
                    },
                    options: {
                        responsive: true,
                        plugins: {
                            legend: {
                                display: false
                            }
                        },
                        scales: {
                            y: {
                                beginAtZero: true,
                                ticks: {
                                    callback: function(value) {
                                        return formatMoney(value);
                                    }
                                }
                            }
                        }
                    }
                });
                
                // Generar plan de acción personalizado
                const planAccion = document.getElementById('plan-accion');
                planAccion.innerHTML = '';
                
                const acciones = [
                    {
                        icon: 'search-dollar',
                        title: 'Auditoría de gastos',
                        description: 'Realiza una revisión detallada de todos tus gastos para identificar áreas de posible reducción.'
                    },
                    {
                        icon: 'handshake',
                        title: 'Negociación con proveedores',
                        description: 'Contacta a tus proveedores para negociar mejores precios o condiciones de pago.'
                    },
                    {
                        icon: 'users-cog',
                        title: 'Optimización de personal',
                        description: 'Evalúa si la plantilla actual es la óptima para el volumen de trabajo.'
                    },
                    {
                        icon: 'bolt',
                        title: 'Reducción de consumos',
                        description: 'Implementa medidas para reducir consumo de energía, agua y otros insumos.'
                    }
                ];
                
                acciones.forEach((accion, index) => {
                    const accionElement = document.createElement('div');
                    accionElement.className = 'flex items-start';
                    accionElement.innerHTML = `
                        <div class="flex-shrink-0 h-10 w-10 rounded-full bg-green-100 flex items-center justify-center mt-1">
                            <i class="fas fa-${accion.icon} text-green-600"></i>
                        </div>
                        <div class="ml-3">
                            <p class="font-medium text-gray-800">${index + 1}. ${accion.title}</p>
                            <p class="text-sm text-gray-600">${accion.description}</p>
                        </div>
                    `;
                    planAccion.appendChild(accionElement);
                });
            }

            // Descargar plan como PDF (simulado)
            document.getElementById('descargar-plan-btn').addEventListener('click', function() {
                alert('¡Función de descarga habilitada! En una implementación real, esto generaría un PDF con tu plan de ahorro personalizado.');
            });
        });
    </script>
</body>
</html>  
