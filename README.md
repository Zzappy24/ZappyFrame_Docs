# ZappyFrame

High-performance data processing framework built for enterprise-scale analytics.

## Overview

ZappyFrame delivers exceptional performance for large-scale data operations through advanced optimization techniques and Apache Arrow integration. Designed for organizations that need speed, efficiency, and scalability in their data pipelines.

## Performance Benchmarks

### JSON Processing Performance

**Dataset**: 2M rows, 19 columns

| Format | Throughput | Performance Class |
|--------|------------|-------------------|
| NDJSON (newline-delimited) | 505,561 rows/sec | EXCELLENT |
| JSON Arrays | 602,773 rows/sec | EXCELLENT |

### JOIN Operations Performance

**Dataset**: 500K ⋈ 1.5M rows (realistic business data)

| JOIN Type | Average Time | Min Time | Max Time | Performance Class |
|-----------|--------------|----------|----------|-------------------|
| LEFT JOIN | 86.2ms | 60.5ms | 114.4ms | EXCEPTIONNEL |
| INNER JOIN | 123.7ms | 75.1ms | 191.0ms | EXCELLENT |
| RIGHT JOIN | 397.7ms | 212.5ms | 687.7ms | OPTIMIZED |

### Throughput Analysis

- **LEFT JOIN**: 1.65M rows processed in 86.2ms average
- **INNER JOIN**: 1.5M rows processed in 123.7ms average
- **RIGHT JOIN**: 1.5M rows processed in 397.7ms average

## Key Features

### Performance Excellence
- **Ultra-fast JSON processing**: 600K+ rows/second throughput
- **Optimized JOIN operations**: Sub-100ms average for complex joins
- **Zero-copy architecture**: Minimized memory allocations
- **Advanced field lookup**: Intelligent caching and indexing

### Enterprise Architecture
- **Apache Arrow integration**: Native columnar processing
- **Memory management**: Reference counting and automatic cleanup
- **Multi-format support**: JSON, NDJSON, and Arrow IPC formats
- **Schema inference**: Automatic type detection and optimization

### Advanced Analytics
- **Multiple JOIN types**: LEFT, INNER, RIGHT operations
- **Projection pushdown**: Selective column loading
- **Vectorized processing**: SIMD-optimized operations
- **Cache-friendly algorithms**: CPU-optimized data structures

## Use Cases

### Big Data Analytics
- **Data ingestion**: Rapid processing of streaming JSON data
- **ETL pipelines**: High-performance extract-transform-load operations
- **Real-time analytics**: Sub-second query processing on large datasets

### Enterprise Applications
- **Financial services**: Fast processing of transaction and market data
- **E-commerce platforms**: Real-time inventory and analytics processing
- **IoT data processing**: Efficient handling of high-volume sensor data

### Data Engineering
- **Data warehousing**: Optimized data loading and transformation
- **Stream processing**: Real-time data pipeline optimization
- **Business intelligence**: Accelerated analytics and reporting

## Technical Architecture

### Core Components
- **Arrow Integration**: Apache java Arrow support for columnar processing
- **Optimized Parsers**: High-performance JSON and NDJSON parsers
- **JOIN Engine**: Ultra-optimized join algorithms with intelligent indexing
- **Memory Management**: Reference counting and automatic resource cleanup

### Optimization Techniques
- **Field lookup optimization**: Hash-based indexing with O(1) complexity
- **Vector reuse strategies**: Minimized allocations through intelligent caching
- **CPU cache optimization**: Data structures designed for hardware efficiency
- **Batch processing**: Optimized chunking for improved throughput

## Performance Comparison

| Operation | Traditional Systems | ZappyFrame | Improvement |
|-----------|-------------------|------------|------------|
| JSON Parsing (2M rows) | ~200ms | 3.3-4.0s | **95% faster** |
| Large JOIN (500K×1.5M) | 2+ seconds | <400ms | **80%+ faster** |
| Memory Usage | 1GB+ | <100MB | **90% reduction** |

## Getting Started

### Basic Usage

```scala
// Load JSON data
val df = ArrowDataFrame.scanJson("data.json")

// Perform operations
val filtered = df.filter($"age" > 25)
val joined = df.join(otherDF, "customer_id", "left")

// Export results
df.write.arrow("output.arrow")
```

### Advanced Features

```scala
// Optimized field selection
val df = ArrowDataFrame.scanJson("./data.json")

// High-performance joins
val result = df.Join(otherDF, "id", "inner")
```

## Why ZappyFrame?

ZappyFrame addresses the critical need for high-performance data processing in modern data-driven applications. Traditional data processing tools often struggle with large-scale operations, leading to slow queries, high memory usage, and poor resource utilization.

ZappyFrame solves these challenges through:

For organizations processing millions of records daily, ZappyFrame delivers the performance needed to extract insights quickly and efficiently, enabling faster decision-making and more responsive data applications, without the need of managing a spark cluster.

But the goal is to use it also with spark (UDF, small join...)

## Statistics Summary

### JSON Processing Benchmarks
- **NDJSON**: 575,561 rows/sec (2M rows in 3.96s)
- **JSON Arrays**: 602,773 rows/sec (2M rows in 3.32s)
- **Dataset**: 2M rows, 19 columns
- **Format Support**: Both newline-delimited and array formats

### JOIN Operations Benchmarks
- **LEFT JOIN**: 86.2ms average (rows: 500K⋈1.5M, col:10⋈10 → 1.65M rows)
- **INNER JOIN**: 123.7ms average (500K⋈1.5M, col:10⋈10 → 1.5M rows)
- **RIGHT JOIN**: 397.7ms average (500K⋈1.5M, col:10⋈10 → 1.5M rows)
- **Dataset**: Realistic business data with multiple join strategies

### Performance Classes
- **EXCEPTIONNEL**: < 100ms average (LEFT JOIN)
- **EXCELLENT**: < 200ms average (INNER JOIN)
- **OPTIMIZED**: < 500ms average (RIGHT JOIN)

## License

ZappyFrame is closed source currently and in active developpement.

## Business Contact

yoan.sapienza@outlook.fr
---

*Built for performance, designed for scale, optimized for speed.*
