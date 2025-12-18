# Qing Veritable Records (清實錄) CSV Viewer

A simple, lightweight historical document viewer for browsing and searching Qing Dynasty Veritable Records (清實錄) data in CSV format.

## Usage

### Basic Usage

1. Place `kxqsl.html` and your CSV file in the same folder
2. Open using a local server (see instructions below)
3. The page will automatically load `qsl_kx.csv`, or specify a file using URL parameters

### Using a Local Server

Due to browser security restrictions, you need to open the file through an HTTP server:

**Python 3:**
```bash
python3 -m http.server 8000
```

**Python 2:**
```bash
python -m SimpleHTTPServer 8000
```

**Node.js (using http-server):**
```bash
npx http-server -p 8000
```

Then open in your browser: `http://localhost:8000/kxqsl.html`

### Specifying a Different CSV File

Add a `csv` parameter to the URL:

```
http://localhost:8000/kxqsl.html?csv=your_file.csv
```

### CSV Format Requirements

The CSV file must include the following columns (header row):
- `volume` - Volume/juan (卷次)
- `year` - Year (年)
- `month` - Month (月)
- `day_ganzhi` - Day in ganzhi (日干支)
- `text` - Main text content (正文內容)

Example:
```csv
volume,year,month,day_ganzhi,text
卷之1,順治十八,正月,辛亥,順治十八年。辛丑。春。正月。...
```

## Keyboard Shortcuts

- `Ctrl+F` / `Cmd+F` - Focus search box
- `ESC` - Clear search and exit search box

## Copy Function

When you select and copy text, the system automatically appends a metadata line to the copied content:

```
Selected text content
《聖祖仁皇帝實錄》, 卷之1, 順治十八, 正月, 辛亥
```

The metadata format: `《Veritable Records of Emperor Shengzu Ren (聖祖仁皇帝實錄)》, volume (卷次), year (年), month (月), day (日干支)`

## License

This project is a personal use tool, free to use and modify.