const { app, BrowserWindow, ipcMain, dialog } = require('electron');
const path = require('path');
const fs = require('fs');

function createWindow() {
  const win = new BrowserWindow({
    width: 1180,
    height: 820,
    minWidth: 980,
    minHeight: 700,
    backgroundColor: '#f3f4f6',
    title: 'Einnahmen-Ausgaben',
    webPreferences: {
      preload: path.join(__dirname, 'preload.js'),
      contextIsolation: true,
      nodeIntegration: false,
      sandbox: false
    },
    icon: path.join(__dirname, '..', 'build', 'icon.ico')
  });

  win.loadFile(path.join(__dirname, '..', 'index.html'));
}

app.setName('Einnahmen-Ausgaben');

app.whenReady().then(() => {
  createWindow();
  app.on('activate', () => {
    if (BrowserWindow.getAllWindows().length === 0) createWindow();
  });
});

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') app.quit();
});

// IPC: Save binary (e.g., Excel)
ipcMain.handle('save-binary-file', async (_event, opts = {}) => {
  try {
    // Support both option shapes used in the renderer:
    // - { defaultPath, data, filters, title }
    // - { defaultFilename, content, filters }
    // - { defaultName, data, filters }  (older renderer variants)
    const filters = Array.isArray(opts.filters) ? opts.filters : undefined;
    const title = opts.title || 'Speichern';

    // Prefer an xlsx default name if nothing is supplied
    // Renderer can pass: defaultPath OR defaultFilename OR defaultName
    let suggested = opts.defaultPath || opts.defaultFilename || opts.defaultName || 'export.xlsx';

    // Data can be provided as ArrayBuffer/Uint8Array/Buffer
    const payload = opts.data ?? opts.content ?? opts.buffer;

    const res = await dialog.showSaveDialog({
      title,
      defaultPath: suggested,
      filters
    });

    if (res.canceled || !res.filePath) return { ok: false, canceled: true };

    if (!payload) return { ok: false, canceled: false, error: 'Keine Daten erhalten.' };

    let outPath = res.filePath;

    // If user didn't type an extension, add .xlsx when filter suggests xlsx or suggested name ends with xlsx
    const wantsXlsx =
      (filters && filters.some(f => (f.extensions || []).includes('xlsx'))) ||
      String(suggested).toLowerCase().endsWith('.xlsx');

    if (wantsXlsx && !/\.xlsx$/i.test(outPath)) {
      outPath += '.xlsx';
    }

    const buf = Buffer.isBuffer(payload)
      ? payload
      : (typeof payload === 'string'
          ? Buffer.from(payload, 'utf8')
          : Buffer.from(new Uint8Array(payload)));

    fs.writeFileSync(outPath, buf);

    return { ok: true, canceled: false, filePath: outPath };
  } catch (err) {
    return { ok: false, canceled: false, error: String(err?.message || err) };
  }
});


// IPC: Fokus auf aktuelles Fenster zurückholen
ipcMain.handle('focus-window', async () => {
  try {
    const win = BrowserWindow.getFocusedWindow() || BrowserWindow.getAllWindows()[0];
    if (win) {
      win.show();
      win.focus();
    }
    return { ok: true };
  } catch (err) {
    return { ok: false, error: String(err?.message || err) };
  }
});
