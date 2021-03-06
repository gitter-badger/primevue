<template>
	<div class="content-section documentation">
		<TabView>
			<TabPanel header="Documentation">
				<h3>Import</h3>
<CodeHighlight lang="javascript">
import FileUpload from 'primevue/fileupload';
</CodeHighlight>

				<h3>Getting Started</h3>
				<p>FileUpload requires a <i>url</i> property as the upload target and a <i>name</i> to identify the files at backend.</p>
<CodeHighlight>
&lt;FileUpload name="demo[]" url="./upload" /&gt;
</CodeHighlight>

				<h3>Multiple Uploads</h3>
				<p>Only one file can be selected at a time by default, to allow selecting multiple files at once enable <i>multiple</i> option.</p>
<CodeHighlight>
&lt;FileUpload name="demo[]" url="./upload" :multiple="true" /&gt;
</CodeHighlight>

				<h3>Basic UI</h3>
				<p>FileUpload basic mode provides a simpler UI as an alternative to advanced mode.</p>
<CodeHighlight>
&lt;FileUpload mode="basic" name="demo[]" url="./upload" /&gt;
</CodeHighlight>

				<h3>DragDrop</h3>
				<p>File selection can also be done by dragging and dropping from the filesystem to the content section of the component.</p>

				<h3>Auto Uploads</h3>
				<p>When <i>auto</i> property is enabled, upload begins as soon as file selection is completed or a file is dropped on the drop area.</p>
<CodeHighlight>
&lt;FileUpload mode="basic" name="demo[]" url="./upload" :auto="true" /&gt;
</CodeHighlight>

				<h3>File Types</h3>
				<p>Selectable file types can be restricted with <i>accept</i> property, example below only allows images to be uploaded. Read more about other possible values <a href="https://www.w3schools.com/tags/att_input_accept.asp"> here</a>.</p>
<CodeHighlight>
&lt;FileUpload mode="basic" name="demo[]" url="./upload" accept="image/*" /&gt;
</CodeHighlight>

				<h3>File Size</h3>
				<p>Maximium file size can be restricted using <i>maxFileSize</i> property defined in bytes.</p>
<CodeHighlight>
&lt;FileUpload name="demo[]" url="./upload" :maxFileSize="1000000" /&gt;
</CodeHighlight>

				<p>In order to customize the default messages use <i>invalidFileSizeMessage</i> option. In messages, {0} placeholder refers to the filename and in detail message, the file size.</p>
				<ul>
					<li>
						invalidFileSizeMessage: '{0}: Invalid file size, file size should be smaller than {1}.'
					</li>
				</ul>

				<h3>Request Customization</h3>
				<p>XHR request to upload the files can be customized using the before-upload callback that passes the xhr instance and FormData object as event parameters.</p>

				<h3>Properties</h3>
				<div class="doc-tablewrapper">
					<table class="doc-table">
						<thead>
                            <tr>
                                <th>Name</th>
                                <th>Type</th>
                                <th>Default</th>
                                <th>Description</th>
                            </tr>
						</thead>
						<tbody>
                            <tr>
                                <td>name</td>
                                <td>string</td>
                                <td>null</td>
                                <td>Name of the request parameter to identify the files at backend.</td>
                            </tr>
                            <tr>
                                <td>url</td>
                                <td>string</td>
                                <td>null</td>
                                <td>Remote url to upload the files.</td>
                            </tr>
                            <tr>
                                <td>mode</td>
                                <td>string</td>
                                <td>advanced</td>
                                <td>Defines the UI of the component, possible values are "advanced" and "basic".</td>
                            </tr>
                            <tr>
                                <td>multiple</td>
                                <td>boolean</td>
                                <td>false</td>
                                <td>Used to select multiple files at once from file dialog.</td>
                            </tr>
                            <tr>
                                <td>accept</td>
                                <td>string</td>
                                <td>false</td>
                                <td>Pattern to restrict the allowed file types such as "image/*".</td>
                            </tr>
                            <tr>
                                <td>disabled</td>
                                <td>boolean</td>
                                <td>false</td>
                                <td>Disables the upload functionality.</td>
                            </tr>
                            <tr>
                                <td>auto</td>
                                <td>boolean</td>
                                <td>false</td>
                                <td>When enabled, upload begins automatically after selection is completed.</td>
                            </tr>
                            <tr>
                                <td>maxFileSize</td>
                                <td>number</td>
                                <td>null</td>
                                <td>Maximum file size allowed in bytes.</td>
                            </tr>
                            <tr>
                                <td>invalidFileSizeMessage</td>
                                <td>string</td>
                                <td>"&#123;0&#125;: Invalid file size, file size should be smaller than &#123;1&#125;."</td>
                                <td>Summary message of the invalid fize size.</td>
                            </tr>
                            <tr>
                                <td>withCredentials</td>
                                <td>boolean</td>
                                <td>false</td>
                                <td>Cross-site Access-Control requests should be made using credentials such as cookies, authorization headers or TLS client certificates.</td>
                            </tr>
                            <tr>
                                <td>previewWidth</td>
                                <td>number</td>
                                <td>50</td>
                                <td>Width of the image thumbnail in pixels.</td>
                            </tr>
                            <tr>
                                <td>chooseLabel</td>
                                <td>string</td>
                                <td>Choose</td>
                                <td>Label of the choose button.</td>
                            </tr>
                            <tr>
                                <td>uploadLabel</td>
                                <td>string</td>
                                <td>Upload</td>
                                <td>Label of the upload button.</td>
                            </tr>
                            <tr>
                                <td>cancelLabel</td>
                                <td>string</td>
                                <td>Cancel</td>
                                <td>Label of the cancel button.</td>
                            </tr>
						</tbody>
					</table>
				</div>

				<h3>Events</h3>
				<div classe="doc-tablewrapper">
					<table class="doc-table">
						<thead>
						<tr>
							<th>Name</th>
							<th>Parameters</th>
							<th>Description</th>
						</tr>
						</thead>
						<tbody>
						<tr>
							<td>before-upload</td>
							<td>event.xhr: XmlHttpRequest instance. <br/>
								event.formData: FormData object.</td>
							<td>Callback to invoke before file upload begins to customize the request
								such as post parameters before the files.</td>
						</tr>
						<tr>
							<td>before-send</td>
							<td>event.xhr: XmlHttpRequest instance. <br/>
								event.formData: FormData object.</td>
							<td>Callback to invoke before file send begins to customize the request
								such as adding headers.</td>
						</tr>
						<tr>
							<td>upload</td>
							<td>event.xhr: XmlHttpRequest instance.<br />
								event.files: Uploaded files.</td>
							<td>Callback to invoke when file upload is complete.</td>
						</tr>
						<tr>
							<td>error</td>
							<td>event.xhr: XmlHttpRequest instance.<br />
								event.files: Files that are not uploaded.</td>
							<td>Callback to invoke if file upload fails.</td>
						</tr>
						<tr>
							<td>clear</td>
							<td>-.</td>
							<td>Callback to invoke when files in queue are removed without uploading.</td>
						</tr>
						<tr>
							<td>select</td>
							<td>event.originalEvent: Original browser event. <br />
								event.files: List of selected files.</td>
							<td>Callback to invoke when file upload is complete.</td>
						</tr>
						<tr>
							<td>progress</td>
							<td>event.originalEvent: Original browser event. <br />
								event.progress: Calculated progress value.</td>
							<td>Callback to invoke when files are selected.</td>
						</tr>
						</tbody>
					</table>
				</div>

				<h3>Styling</h3>
				<p>Following is the list of structural style classes, for theming classes visit <router-link to="/theming">theming</router-link> page.</p>
				<div class="doc-tablewrapper">
					<table class="doc-table">
						<thead>
						<tr>
							<th>Name</th>
							<th>Element</th>
						</tr>
						</thead>
						<tbody>
						<tr>
							<td>p-fileupload</td>
							<td>Container element.</td>
						</tr>
						<tr>
							<td>p-fileupload-buttonbar</td>
							<td>Header containing the buttons.</td>
						</tr>
						<tr>
							<td>p-fileupload-content</td>
							<td>Content section.</td>
						</tr>
						</tbody>
					</table>
				</div>

				<h3>Dependencies</h3>
				<p>None.</p>
			</TabPanel>

			<TabPanel header="Source">
				<a href="https://github.com/primefaces/primevue/tree/master/src/views/fileupload" class="btn-viewsource" target="_blank" rel="noopener noreferrer">
					<span>View on GitHub</span>
				</a>
<CodeHighlight>
<template v-pre>
&lt;template&gt;
	&lt;div&gt;
		&lt;div class="content-section introduction"&gt;
			&lt;div class="feature-intro"&gt;
				&lt;h1&gt;FileUpload&lt;/h1&gt;
				&lt;p&gt;FileUpload is an advanced uploader with dragdrop support, multi file uploads, auto uploading, progress tracking and validations.&lt;/p&gt;
			&lt;/div&gt;
		&lt;/div&gt;

		&lt;div class="content-section implementation"&gt;
			&lt;h3&gt;Advanced&lt;/h3&gt;
			&lt;FileUpload name="demo[]" url="./upload.php" @upload="onUpload" :multiple="true" accept="image/*" :maxFileSize="1000000" /&gt;

			&lt;h3&gt;Basic&lt;/h3&gt;
			&lt;FileUpload mode="basic" name="demo[]" url="./upload.php" accept="image/*" :maxFileSize="1000000" @upload="onUpload" /&gt;

			&lt;h3&gt;Basic with Auto&lt;/h3&gt;
			&lt;FileUpload mode="basic" name="demo[]" url="./upload.php" accept="image/*" :maxFileSize="1000000" @upload="onUpload" :auto="true" chooseLabel="Browse" /&gt;
		&lt;/div&gt;
	&lt;/div&gt;
&lt;/template&gt;
</template>
</CodeHighlight>

<CodeHighlight lang="javascript">
export default {
	methods: {
		onUpload() {
			this.$toast.add({severity: 'info', summary: 'Success', detail: 'File Uploaded', life: 3000});
		}
	}
}
</CodeHighlight>
			</TabPanel>
		</TabView>
	</div>
</template>