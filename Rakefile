desc 'vt-optimizer'
task :view do
  sh 'node ../vt-optimizer/index.js -m ../jp_medical_area2014/pma-tiles/pma.mbtiles'
end

desc 'build docs/zxy tiles'
task :tiles do
  sh "tile-join --force --no-tile-compression\
    --output-to-directory=docs/zxy/pma --maximum-zoom=12\
    --no-tile-size-limit ../jp_medical_area2014/pma-tiles/pma.mbtiles"
  sh "tile-join --force --no-tile-compression\
    --output-to-directory=docs/zxy/sma --maximum-zoom=12\
    --no-tile-size-limit ../jp_medical_area2014/sma-tiles/sma.mbtiles"
end

desc 'build docs/style.json'
task :style do
  sh 'parse-hocon hocon/style.conf > docs/style.json'
  sh 'gl-style-validate docs/style.json'
end

desc 'locally host the site'
task :host do
  sh 'budo -d docs'
end

